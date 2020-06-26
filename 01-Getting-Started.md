---
title: 01-Getting-Started
created: "2020-06-20T09:04:14.210Z"
modified: "2020-06-21T07:54:55.028Z"
---

# 01-Getting-Started

## Verify installation

`docker version`  
`docker info`

```
> docker version

Client: Docker Engine - Community
 Version:           19.03.8
 API version:       1.40
 Go version:        go1.12.17
 Git commit:        afacb8b
 Built:             Wed Mar 11 01:23:10 2020
 OS/Arch:           windows/amd64
 Experimental:      false

Server: Docker Engine - Community
 Engine:
  Version:          19.03.8
  API version:      1.40 (minimum version 1.12)
  Go version:       go1.12.17
  Git commit:       afacb8b
  Built:            Wed Mar 11 01:29:16 2020
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          v1.2.13
  GitCommit:        7ad184331fa3e55e52b890ea95e65ba581ae3429
 runc:
  Version:          1.0.0-rc10
  GitCommit:        dc9208a3303feef5b3839f4323d9beb36df0a9dd
 docker-init:
  Version:          0.18.0
  GitCommit:        fec3683
```

## Images and Container

Basic test run  
`docker container run hello-world`  
`docker container run busybox echo Hallow World`

| new command              | old command    |
| ------------------------ | -------------- |
| docker image ls          | docker images  |
| docker container run     | docker run     |
| docker container create  | docker create  |
| docker container start   | docker start   |
| docker container stop    | docker stop    |
| docker container pull    | docker pull    |
| docker container ps      | docker ps      |
| docker container logs    | docker logs    |
| docker container kill    | docker kill    |
| docker container rm      | docker rm      |
| docker container inspect | docker inspect |

`docker run` = `docker create` + `docker start`

List all images  
`docker image ls --all`  
`docker images --all`  
`docker images -a`

Start a nginx server, publish from port 80 to 8080, name it `web001`, run in the background  
`docker container run --publish 8080:80 --name web001 --detach nginx`  
<small>To test above webserver, open http://localhost:8080 in browser</small>

List running container  
`docker container ps`  
`docker ps`

List all containers that are running and previously run  
`docker container ps --all`  
`docker ps -a`  
`docker ps --all`

Stop a container by name `web001`  
`docker container stop web001`

Restart a container by name `web001`  
`docker container start web001`

View logs of container `web001`  
`docker container logs web001`

View process running in container `web001`  
`docker container top web001`

Start a mongo db server, name it `mongodb`  
`docker container run --name mongodb mongo`

Start a mongo db server, name it `mongodb`, run in the background  
`docker container run --name mongodb --detach mongo`

Remove container by container ID or name  
`docker container rm web001 web002 mongodb`

**Run multiple containers**

- Run httpd (apache) on 8080
- Run nginx on port 8081
- Run mysql on 3306, set MYSQL*RANDOM_ROOT_PASSWORD  
  <small>More info about mysql: https://hub.docker.com/*/mysql </small>

```
docker container run --detach --name web1 --publish 8080:80 httpd
docker container run --detach --name web2 --publish 8081:80 nginx
docker container run --detach --name db1 --publish 3306:3306 -e MYSQL_RANDOM_ROOT_PASSWORD:yes mysql
```

Inspect container - Display detailed information on one or more containers by name `web001`  
`docker container inspect web001`

Display a live stream of container(s) resource usage statistics  
`docker container stats`  
`docker container stats web001`

## Docker container with shell (interactive mode)

Start ubuntu container with shell, name `ub1` ^SC#1^  
`docker container run -it --name ub1 ubuntu`

Start ubuntu container, name `ub2` ^SC#2^  
`docker container run --name ub2 ubuntu`

When we executed ^SC#1^ above, we can restart container and get the shell again with `docker start -ai ub1`.  
But we cannot restart container ^SC#2^ and get the shell with `docker start -ai ub2`.

```
 -it are actually two options/parameters
 -i, --interactive                    Keep STDIN open even if not attached
 -t, --tty                            Allocate a pseudo-TTY
```

Difference between starting container with `-it` and without `-it`, as show in `docker container inspect` of ubuntu container above.

| with `-it`           | without `-it`         |
| -------------------- | --------------------- |
| "AttachStdin": true, | "AttachStdin": false, |
| "Tty": true,         | "Tty": false,         |
| "OpenStdin": true,   | "OpenStdin": false,   |
| "StdinOnce": true,   | "StdinOnce": false,   |

```
"Cmd": [
    "/bin/bash"
],
"Image": "ubuntu",
```

Execute command from a running container  
`docker container run --name web1 --detach nginx` <small>Start and run a nginx container, name it `web1`</small>  
`docker exec -it web1 echo something good will come` <small>Execute echo to print somet text</small>

Override default commands when starting a container  
`docker container run -it --name proxy nginx bash` <small>This will execute bash</small>

---

### Side-notes

To install `ping` and `curl` in ubuntu

```
apt-get update
apt-get install iputils-ping
apt-get install curl
```

To install `curl` in alpine

```
apk get curl
```

### docker container

```
> docker container --help
Usage:  docker container COMMAND
Manage containers
Commands:
  attach      Attach local standard input, output, and error streams to a running container
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  inspect     Display detailed information on one or more containers
  kill        Kill one or more running containers
  logs        Fetch the logs of a container
  ls          List containers
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  prune       Remove all stopped containers
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  run         Run a command in a new container
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  wait        Block until one or more containers stop, then print their exit codes

Run 'docker container COMMAND --help' for more information on a command.
```
