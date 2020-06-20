---
title: 01-Getting-Started
created: '2020-06-20T09:04:14.210Z'
modified: '2020-06-20T14:52:49.680Z'
---

# 01-Getting-Started

## Verify installation
`docker version`
`docker info`

## Images and Container

Basic test run
`docker container run hello-world`
`docker container run busybox echo Hallow World`

| new command                | old command     | remarks        |
|----------------------      |--------------   |-----------     |         
| docker image ls            | docker images   |  
| docker container run       | docker run      | 
| docker container create    | docker create   | 
| docker container start     | docker start    | 
| docker container stop      | docker stop     | 
| docker container pull      | docker pull     | 
| docker container ps        | docker ps       |
| docker container logs      | docker logs     |
| docker container kill      | docker kill     |
| docker container rm        | docker rm       |

`docker run` = `docker create` + `docker start`

List all images
`docker image ls --all`
`docker images --all`

Start a nginx server, publish from port 80 to 8080, name it `web001`, run in the background
`docker container run --publish 8080:80 --name web001 --detach nginx`
> To test above webserver, open http://localhost:8080 in browser 

List running container
`docker container ps`

List all containers that are running and previously run
`docker container ps --all`

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

### Exercise 1 - Run multiple containers
+ Run httpd (apache) on 8080
+ Run nginx on port 8081
+ Run mysql on 3306, set MYSQL_RANDOM_ROOT_PASSWORD
More info about mysql: https://hub.docker.com/_/mysql

```
docker container run --detach --name web1 --publish 8080:80 httpd
docker container run --detach --name web2 --publish 8081:80 nginx
docker container run --detach --name db1 --publish 3306:3306 -e MYSQL_RANDOM_ROOT_PASSWORD:yes mysql
```

