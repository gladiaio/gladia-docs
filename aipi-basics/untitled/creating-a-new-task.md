# Creating a new task

In case the Task in the INPUT/OUTPUT combination doesn't exists don't hesitate to create one, it's simple.



## General concepts

1\) add a file named with the task name for instance : super-resolution.py in image/image

{% embed url="https://github.com/theunifai/unifai-apis-core/tree/main/src/apis/image/image" %}

2\) the content of the file should be similar to this one

{% embed url="https://gist.github.com/jqueguiner/de860a0d3be95771d536f8c4e81ea1d9" %}

## Understanding the details of a task routeur

### Mandatory imports

```python
# mandatory imports to declare your task in the application
from fastapi import APIRouter
from unifai_api_utils.submodules import TaskRouter
```

### Declaring inputs

```python
# declare inputs you can have as many inputs as you want
input = [
    {
        # Declare the type of input
        # could be image / sound / video / text / number / json
        "type": "image",
        # set the name of the input ; this needs to be unique for the given task
        "name": "image",
        # default value that will be set in the swagger
        "default": "Image to restore",
        # placeholder is used for display within a textbox for instance
        "placeholder": "Image to restore",
        # tooltip will be used in the frontend when the user move over the input field for further infos
        "tooltip": "Insert the image to restore",
    },
]

```

### Declaring outputs

```python
# output is unique only one output is set
# if the task returns multiple files they will be ZIPPED into 1 unique archive
output = {
        # name of output
        "name": "enhanced_image",
        # type of the output coule be image / sound / video / text / number / json
        "type": "image",
        # example of input (displayed in the fronted before execution) for now only text is supported but soon image / video / sound will be also supported
        "example": "enhanced_image"
    }
```

### Registering the API Task route

```python
# declare a new APIrouter in FastAPI
router = APIRouter()

# Declare the Task routeur with it's input / output and default_model
TaskRouter(router=router, input=input, output=output, default_model="esrgan")
```

### Need help ?

{% embed url="https://6k1rdwg6stf.typeform.com/to/G5n56NCr" %}

