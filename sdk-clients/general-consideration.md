# General consideration

SDK are built based on OpenAPI Generator [https://github.com/OpenAPITools/openapi-generator](https://github.com/OpenAPITools/openapi-generator)



{% embed url="https://github.com/theunifai/unifai-sdk" %}

## Building all SDKs

You can build all SDKs using the SDK generator.

{% embed url="https://github.com/theunifai/unifai-sdk/tree/main/generator" %}

```shell
# build the docker image
$ docker build -t unifai-apis -f gpu.Dockerfile . 
​
# run docker for dev
$ docker run -d -v $PWD:/app -p 8080:80 unifai-apis

# or run docker for prod
$ docker run -d -p 8080:80 unifai-apis

# clone the SDK generator
cd ~
git clone https://github.com/theunifai/unifai-sdk.git

# generate SDKs
cd unifai-sdk/generator
python3 generate_sdk.py http://localhost:8080/

# SDK will be available here
cd ~/unifai-sdk/clients
```

