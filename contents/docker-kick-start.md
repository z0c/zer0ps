# Docker

This is a minimalistic introduction to docker.

Docker is a program that runs operating system lever virtualization (containers).

This gives a lot of the resource isolation features of virtualization without the overhead of starting and maintaining VM's.

## Before you begin

I'm using ArchLinux, some of the commands need to be adapted for other distros.

`${container_id}` and `${container_name}` are often interchangable in commands.

## Setup

### Install docker package
```
$ sudo pacman -S docker
```
### Setup

Manage docker as a non-root user:

Create `docker` group:
```
$ sudo groupadd docker
```

Add your user to `docker` group:
```
$ sudo usermod -aG docker $USER
```

You will need to logout for your profile to pick the changes.

### Starting on boot
```
$ sudo systemctl enable docker && sudo systemctl start docker
```

### Test
```
$ docker run hello-world
```

## Images

Docker commands for image related operations

### List images
```
$ docker images
```

### Download an image
```
$ docker pull ${image_name}
```

### Delete an image
```
$ docker rmi ${image_name}
```

## Containers

Docker commands for interacting with containers

### Start a container
```
$ docker run ${image_name}
```

### List running containers
```
$ docker ps
```

* `-a` to list all, including non running containers

### Run interactivelly
```
$ docker run -it ${image_name} sh
```

### Removing a container
```
$ docker rm ${container_id}
```

### Removing all exited containers
```
$ docker rm $(docker ps -a -q -f status=exited)
```

* `-a` all
* `-q` returns only container id's
* `-f` filter

## Applications

### Runing an application
```
$ docker run -d -P --name ${friendly_name} ${image_name}
```

* `-d` Runs the container process demonized
* `-P` Publishes exposed ports on random ports on the host
* `--name` Gives a friendly name to the container process

### Listing exposed ports
```
$ docker port ${container_id}
```

### Runing with explicit ports
```
$ docker run -p 8888:80 ${image_name}
```

* `-p` Explicit port flag
* `8888` Host port
* `80` Container port

### Entering a running container

You can enter a container an run commands as if you had ssh'ed

```
$ docker exec -it ${container_id} sh
```

### Stopping a running container
```
$ docker stop ${container_id}
```

## Reference

* [Getting started](https://docker-curriculum.com/ )
* [Linux post install](https://docs.docker.com/install/linux/linux-postinstall/ )
* [Docker hub image repository](https://hub.docker.com/ )

