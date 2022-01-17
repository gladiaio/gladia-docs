# Installation and deployment

Considering the complexity of the GPU driver matching the CUDA version, the CuDNN version combined with Tensorflow GPU, Torch etc.. we strongly recommend to use our Docker distribution.

## Building the Docker image

```shell
git clone https://github.com/gladiaio/gladia.git
cd gladia/api

#building the development Docker Image
docker build -t gladia -f gpu.Dockerfile.dev .

# OR
#building the production Docker Image
docker build -t gladia -f gpu.Dockerfile.prod .
```

## Running the Docker image

### Running for real-time development

This can help you for live debug as you can edit you local code and see changes occurring live thanks to the volume attachment (-v).

```shell
docker run -it --name gladia -p 8080:80 -v $PWD:/app gladia-apis
# OR more simply use our wrapper
./build_and_dev.sh
```

### Running in production

In this case the code is fully packaged in the Docker Image and has no data link with the host (meaning no attached volume). Also you don't see live logs from the container because you ran it in a detached (-d) mode.

```shell
docker run -d --name gladia -p 8080:80 unifai
# OR more simply use our wrapper
./build_and_prod.sh
```

### What's next ?

```
# checking that your container actually runs
docker ps
```

```
# checking the livelogs from your container
docker logs -f gladia
```
