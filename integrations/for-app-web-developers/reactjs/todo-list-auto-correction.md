---
description: >-
  Let's see how to use the Gladia's JavaScript SDK in your ReactJS Web
  application.
---

# Todo List : Auto-correction

### How to integrate Gladia to your web application&#x20;

Gladia provide a multitude of ready-of-use SDKs allowing you to integrate Gladia in most of your web-application. You can find the list of those SDK on [this repository](https://github.com/gladiaio/gladia-sdk/tree/main/clients).

In this example we will see how to integrate Gladia into a ReactJS web application using the JavaScript SDK. You can find the source-code of the example [here](https://github.com/gladiaio/gladia-examples/tree/main/todo-list).

#### JavaScript SDK installation

First you need to install the JavaScript client (we are currently working on deploying a npm package to make it easier for you to use Gladia) to communicate with Gladia's API.

To install the JS client we provide you [this script](https://github.com/gladiaio/gladia-examples/blob/main/todo-list/init.sh) that install it for you. If you prefer to install it manually you can executing the following commands in the project directory:

```bash
# Clone Gladia's clients
git clone https://github.com/gladiaio/gladia-sdk.git /tmp/gladia-sdk

# Install Gladia's JS client and its dependencies
npm install --save /tmp/gladia-sdk/clients/javascript
npm install querystring
npm install superagent

# Install project's dependencies
npm install
```

#### AutoCorrection integration

Let's imagine a simple TodoList implemented in ReactJs. To add a new element to our todo-list we have a `useState` like this

```jsx
const [tasks, setTasks] = useState([])
```

a `task` is represented as an object compose of a string named `task` and an uuid named `id`.



For each new task we want to be sure there is now typo, for that we can use the `autocorrect` task from Gladia's API. Let's start by importing and initializing our client:

```javascript
import { TextTextAutocorrectApi } from 'fast_api/src'

const api = new TextTextAutocorrectApi()
```



Now that our client is initialized we can make our first call to the `autocorrect` task like this:

```javascript
api.applyTextTextAutocorrectPost({
    'sentence': SENTENCE_TO_CORRECT,
    'model': MODEL_TO_USE
}, CALLBACK_TO_USE)
```

Let's unpack the differents parameters:

* `SENTENCE_TO_CORRECT` is the sentence that you want to apply `autocorrect` on.
* `MODEL_TO_USE` is the model that you want to use, you can list the available models on this route (GET) `text/text/autocorrect/`.
* `CALLBACK_TO_USE` since the JavaScript SDK is based on  `superagent` you can resolve the promise by a simple `.then()`, you need to provide a callback to call once the promise is resolved.

In our case `SENTENCE_TO_CORRECT` is equal to our state `task` , `MODEL_TO_USE` to `flexudy-t5-base-multi-sentence-doctor` and we define `CALLBACK_TO_USE` as follow:

```jsx
const apiCallback = (error, data, response) => {
  if (error) {
    console.error(error)
  } else {
    setTasks([{ // add the corrected tasks to our tasks list
      "task": data, // define the task's content
      "id": uuidv4() // define the task's id
    }, ...tasks])
  }
}
```

and voila! Your first Gladia integration, easy isn't it?
