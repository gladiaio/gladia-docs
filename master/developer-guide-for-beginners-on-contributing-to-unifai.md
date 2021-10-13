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

#building the development Docker Image
docker build -t unifAI-APIs -f gpu.Dockerfile.dev .

#building the production Docker Image
docker build -t unifAI-APIs -f gpu.Dockerfile.prod .
```

## Running the Docker image

{% content-ref url="../aipi-basics/install.md" %}
[install.md](../aipi-basics/install.md)
{% endcontent-ref %}

 
