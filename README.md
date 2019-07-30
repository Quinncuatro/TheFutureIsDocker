# LTP Magazine - The Future Is Docker

#### Docker && CentOS && Apache

These are the commands that are outlined in the article on how to build, manage, and destroy Docker images and containers.

## Build

Copy the sources down and do the build:

``` bash
$ docker build --rm -t quinncuatro/dockerdemo .
```

## Images

View images currently on your system:

``` bash
$ docker images
```

## Run

Change directory and run container:

``` bash
$ cd ../CodeProjects/DaveBeingSassy/

$ docker run -d -p 80 --name Project1 --mount type=bind,source="$(pwd)"/app/,target=/var/www/html/ quinncuatro/dockerdemo
```

## Browse

We need to find the port we want to navigate to:

``` bash
$ docker ps -a

$ curl http://localhost:<port>
```

Alternatively, direct your browser to: http://localhost:<port>

## Exec

Enter a shell session in a container:

``` bash
$ docker exec -it Project1 /bin/bash
```

## Cleanup

Stop a container, delete the container, delete the base image:

``` bash
$ docker stop Project1

$ docker rm Project1

$ docker rmi quinncuatro/dockerdemo
```
