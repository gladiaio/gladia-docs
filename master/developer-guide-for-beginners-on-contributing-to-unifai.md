---
description: >-
  Assuming you have some basic knowledge of Python, this guide should help you
  understand how to make code changes to UnifAI.
---

# Developer guide for beginners on contributing to UnifAI

## Librairies

Most external libraries are embedded in the project in the [requirements.txt](https://github.com/jqueguiner/unifai-apis-core/blob/main/api/requirements.txt) file. The main packages are also embedded in the [Docker base image](https://github.com/jqueguiner/unifai-apis-core/blob/main/api/gpu.Dockerfile.full).

In general for a developer needing a custom library it's recommended to add it to the [requirements.txt](https://github.com/jqueguiner/unifai-apis-core/blob/main/api/requirements.txt) file.

## Building the Docker image

```bash
git clone https://github.com/jqueguiner/unifai-apis-core.git
cd unifai-apis-core/api
docker build -t unifAI-APIs -f gpu.Dockerfile.full .
```

## Running the Docker image

### Running for realtime development

This can help you for live debug as you can edit you local code and see changes occuring live thanks to the volume attachement (-v).

```shell
docker run -it -p 8080:80 -v $PWD:/app unifAI-APIs
```

### Running in production

In this case the code is fully packaged in the Docker Image and has no data link with the host (meaning no attached volume). Also you don't see live logs from the container because you ran it in a detached (-d) mode.

```
docker run -d --name unifAI-APIs -p 8080:80 unifAI-APIs
```

```shell
# checking that your container actually runs
docker ps
```

```
# checking the live logs from your container
docker logs -f unifAI-APIs
```

 
