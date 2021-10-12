# Architecture

## Dependency

The general architecture relies on [FastAPI](https://fastapi.tiangolo.com) framework which is a lightweight web framework for building APIs with Python 3.6+.

## Application routing

![UnifAI general Scaffoding architecture leveraging FastAPI APIRouter](<../../.gitbook/assets/Untitled Diagram.drawio(3) (1).png>)

We leveraged FastAPI with [FastAPI APIRouteurs](https://fastapi.tiangolo.com/tutorial/bigger-applications/#apirouter) in order to better classify our AI tasks' APIs.

{% embed url="https://viewer.diagrams.net/?edit=_blank&highlight=0000ff&layers=1&nav=1#G1cZ54If8Qpf7RZ3dNpzChjOCHBEHz6krw" %}

## AI APIs classification

All the concept relies on the AI problem definitions being split across INPUT types (image, sound, video or text) and OUTPUT types (image, sound, video or text). See the Input/Output/Task [section](../../aipi-basics/input-ouput-tasks.md) for more details.

## Application packaging and deployment

All the framework (for now) is embedded in a [Docker](https://github.com/jqueguiner/unifai-apis-core/blob/main/api/gpu.Dockerfile.full) running a [uvicorn](https://www.uvicorn.org) server.

All the UnifAI AI APIs can be run with a simple command

```
$ git clone https://github.com/jqueguiner/unifai-apis-core.git
$ cd unifai-apis-core/api && docker build -t unifAI-APIs -f gpu.Dockerfile.full .
$ docker run -d -p 8080:80 -v $PWD:/app unifAI-APIs
```

