# Task Router

The task router is the brain of the framework. This is where you API requests lands and is redirected to the appropriate Model.

## Task Routing

The task routing is done through the path of the URL:

URL : `http(s)://`_`YOUR_URL:YOUR_PORT`_`/`_`INPUT_TYPE`_`/`_`OUTPUT_TYPE`_`/`_`TASK`_`/`

For instance image colorization results in :

URL : `http(s)://`_`YOUR_URL:YOUR_PORT`_`/image/image/colorization/`

## Model Routing

Model are being selected through a URL Query String [https://en.wikipedia.org/wiki/Query_string](https://en.wikipedia.org/wiki/Query_string)

URL : `http(s)://`_`YOUR_URL:YOUR_PORT`_`/`_`INPUT_TYPE`_`/`_`OUTPUT_TYPE`_`/`_`TASK?model=my_model`_

For instance image colorization results in :

URL : `http(s)://`_`YOUR_URL:YOUR_PORT`_`/image/image/colorization?model=deoldify-stable`
