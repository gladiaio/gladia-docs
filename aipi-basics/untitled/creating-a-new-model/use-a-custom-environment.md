# Use a custom environment

It can happen that the default environment doesnt fit your needs in this case you can create custom on the fly environments.

#### Environment file

An on the fly custom environment will be spawn for your API based on the pipenv mechanism.

You can set a custom python version as well as custom packages.

{% embed url="https://gist.github.com/jqueguiner/d4382ebe7e14b8af8252053cb1832ab0" %}

Once this environment file set you can build it with a simple command within the docker.

```shell
# Building all custom environments
$ python3 /app/setup_custom_envs.py
```

You are all set you can now run your API within the docker.

```
# build the docker image
$ docker build -t gladia -f gpu.Dockerfile . 

# run docker for dev
$ docker run -it -v $PWD:/app -p 8080:80 gladia /bin/bash

# run the application server
$ uvicorn main:app --host 0.0.0.0 --port 80
```
