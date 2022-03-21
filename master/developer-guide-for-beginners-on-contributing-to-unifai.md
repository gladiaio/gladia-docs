---
description: >-
  Assuming you have some basic knowledge of Python, this guide should help you
  understand how to make code changes to Gladia.
---

# Developer guide for beginners on contributing to Gladia

## Librairies

Most external libraries are embedded in the project in the [requirements.txt](https://github.com/jqueguiner/unifai-apis-core/blob/main/api/requirements.txt) file. The main packages are also embedded in the [Docker base image](https://github.com/jqueguiner/unifai-apis-core/blob/main/api/gpu.Dockerfile.full).

In general for a developer needing a custom library it's recommended to add it to the [requirements.txt](https://github.com/jqueguiner/unifai-apis-core/blob/main/api/requirements.txt) file.

## Building the Docker image

```bash
git clone https://github.com/gladiaio/gladia.git
cd gladia/src

#building the development Docker Image
docker build --target dev -t gladia -f gpu.Dockerfile .

#building the production Docker Image
docker build --target prod -t gladia -f gpu.Dockerfile .
```

## Running the Docker image

{% content-ref url="../aipi-basics/install.md" %}
[install.md](../aipi-basics/install.md)
{% endcontent-ref %}
