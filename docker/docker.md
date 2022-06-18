# Docker Cheat sheet

In order to find your way through the docker command line is to know its structure and know how to navigate in the help
``` bash
docker --help
```
``` bash
docker build --help
```
There are two types of commands:
* Management commands : command that manage only a particular object in docker such as containers or images  
> docker container prune 
* Commands: general commands that are applied on all objects


## 1. Containers 
### 1.1 Running a new Container
The command used to create container is __run__ 
``` docker
 docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```
OPTIONS often used are:
* --detach, -d : Run container in background and print container ID
* --env, -e : Set environment variables (default )
* --interactive, -i : Keep STDIN open even if not attached
* --publish, -p : Publish a container's port(s) to the host
* --volume, -v  : (1) Bind mount a volume
* --volume-driver, -v  : (2) Optional volume driver for the container
* --volumes-from, -v : (3) Mount volumes from the specified container(s)
* --unlimit, -t : Allocate a pseudo-TTY

> start new container from an image already exists in docker hub/local 
``` bash
docker run hello-world
docker run --name mycontiner hello-world
```
> start a container in an interactive mode, using a bash for instance 
``` bash
docker run -it ubuntu bash
```
> start a container with port mapping
``` bash
docker run -p 8080:80 nginx 
```
> start a container with port mapping and env variable
``` bash
docker run -d -p 80:5000 -e PORT=5000 --name webapp nginx
```

### 1.2 Managing Container
> list running containers
``` bash
docker run -p8080:80 nginx 
```
> list all created containers 
``` bash
docker ps -a
```
> remove a containing ( force delete for running containers) 
``` bash
docker rm -f <CONTAINER_ID/CONTAINER_NAME>
```
> delete stopped containres
``` bash
docker container prune
```

> start/stop a container
``` bash
docker start <CONTAINER_ID/CONTAINER_NAME>
docker stop <CONTAINER_ID/CONTAINER_NAME>
```
> rename  a container
``` bash
docker rename OLD_NAME NEW_NAME
```

## 2. Images 
### Create image
> Create an image ..... with a particular starting command 

> create an image from a docker file 
``` bash
docker build -t 
```

> Save an image into tar file
``` bash
docker save IMAGE_NAME > IMAGE_NAME.tar  
```

> Load an image from a tar archive
``` bash
docker load < IMAGE_NAME.tar  
```




## 3. Network 

## 4. Volumes 

















#### resources
* [The Ultimate Docker Cheat Sheet](https://dockerlabs.collabnix.com/docker/cheatsheet/)

