# Creating a new model

Once you have decide in hich input/output category your API should go in.

#### 1) Clone the repo

```bash
# clone the framework from github
git clone https://github.com/theunifai/unifai-apis-core.git
```

#### 2) Create a task if it doesn't exists

If the model you want to implement (for instance ersgan) belongs to a task that doesn't exist (image/image/super-resolution) you will need to create a task first.

Please refere to the Creating a new task guide

{% content-ref url="../../creating-a-new-task.md" %}
[creating-a-new-task.md](../../creating-a-new-task.md)
{% endcontent-ref %}

#### 3) Create a model folder in the task directory to host your API

```bash
# create the folder under the task directory
# for instance for a new super-resolution model
$ mkdir -p unifai-apis-core/src/apis/image/image/super-resolutions/my-new-model

# register the model in the application
$ touch unifai-apis-core/src/apis/image/image/super-resolutions/my-new-model/__init__.py

```

#### 4) create a python file as an entrypoint for the API

The python file that will be the entrypoint of your API should be named like your model like presented below

```shell
# creating the python entrypoint file for the new model API.
$ touch unifai-apis-core/src/apis/image/image/super-resolutions/my-new-model/my-new-model.py
```



