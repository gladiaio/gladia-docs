# Use the default environment

You can use the default environment to build you API however you might need to use custom packages that are not compatible with the default environment in this case feel free to check the [custom environment section](use-a-custom-environment.md).

The default environment is based on Kaggle Docker image : [https://github.com/gladiaio/docker-base](https://github.com/gladiaio/docker-base)

The default envionment have the following packages installed:

{% embed url="https://github.com/gladiaio/gladia/blob/main/src/requirements.txt" %}

{% embed url="https://github.com/gladiaio/docker-base/blob/main/gpu.Dockerfile#L76" %}

### Create your API file

The api file named based on your model (my-model.py) in the input/output/task folder.

here is an example for background removal task for the xception model.

{% embed url="https://github.com/gladiaio/gladia/blob/main/src/apis/image/image/background-removals/xception/xception.py" %}

{% embed url="https://gist.github.com/jqueguiner/fd6d6c87c5e64312925f0fba13180413" %}

you should notice that based on the task the predict function has inputs names as parameter.

the task background is expecting an image as a input and an image as output

here is an other example for text to text sentiment analysis

{% embed url="https://github.com/gladiaio/gladia/tree/main/src/apis/text/text/sentiment-analyses/distilbert-base-uncased-finetuned-sst-2-english" %}

{% embed url="https://gist.github.com/jqueguiner/7a91f701699805ffe445398c20645700" %}

#### Run the application

```shell
# build the docker image
$ docker build -t gladia -f gpu.Dockerfile . 

# run docker for dev
$ docker run -it -v $PWD:/app -p 8080:80 gladia /bin/bash

# run the application server
$ uvicorn main:app --host 0.0.0.0 --port 80
```
