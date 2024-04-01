# Docker

Use docker to create a defined environment, so the application runs on every machine.
Thanks to [YT](https://www.youtube.com/watch?v=pTFZFxd4hOI).

> Resources
>
> [YT](https://www.youtube.com/watch?v=pTFZFxd4hOI)
>
> [Docker](https://docs.docker.com/get-started/)


## virtual machine vs container

### Virtual Machines
A virtual machine, "vm", is a hypervisor, such as Virtualbox, VMWare, Hyper-v
Problems:
 - Each vm needs a complete OS
 - Slow to start
 - resource intensive


### Containers
  - allow running multiple apps in isolation
  - lightweight
  - use the os of the host
  - start quickly (under a  second)
  - less recouse intensive. 10 - 100 docker containers can runn concurrently

## Docker architecture
 - The docker engine runs as a "application" in your os.
 - The docker  engine makes use of the os kernel. the container you run is depending on the kernel type. linux can run linux containers. windows can run windows and linux containers. mac uses a linux vm to run linux containers

## Install docker

 [download](https://docs.docker.com/get-docker/)

 check your version

 ```sh
 docker version
 ```

 ## developement workflow

 we take an application and `dockerize` it by creating a dockerfile

 a docker image contains
  - cut down os
  - runtime environment
  - application files
  - third party libs
  - env variables

  with the dockerfile, dockerfile can package our application to an `image`. images are immutable

## build your first image

 - select a base image from the Docker Registry [Hub](https://hub.docker.com/). select what you need, python, node, ..
 - 

```js title="app.js"
 console.log("Hello from Docker");
```
dsa
 
```title="Dockerfile"
FROM node:alpine
COPY . /app
WORKDIR /app
CMD node app.js
```
Build the docker image. `-t` is the name tag.

```sh
cd <working_dir>
docker build -t hello-docker .
```

Show installed docker repositories.

```sh
docker image ls
```

Run the docker image with the following command.

```sh
docker run hello-docker
```

## from existing workspace

[vscode devcontainers open existing](https://code.visualstudio.com/docs/devcontainers/containers#_open-an-existing-workspace-in-a-container)

[vscode devcontainers getting started](https://code.visualstudio.com/docs/devcontainers/containers#_quick-start-open-an-existing-folder-in-a-container)

 Project template for optimizing:
 
 [https://github.com/cpp-best-practices/cmake_template](https://github.com/cpp-best-practices/cmake_template)


## Package managers

 - conan.io
 - vpkg (windows)
 - cpm (lightweight)
 - system managers like apt
 - raw git pull && cmake