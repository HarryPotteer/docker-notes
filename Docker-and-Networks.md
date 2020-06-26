---
title: Docker-and-Networks
created: '2020-06-21T06:27:09.330Z'
modified: '2020-06-26T03:52:40.516Z'
---

# Docker-and-Networks

**Recap** ~ to start nginx container, and publish port 80 from container to port 8080 in host.  
`docker container run --publish 8080:80 --name web1 --detach nginx`  
`docker container run -p 8080:80 --name web1 -d nginx`

Verify port configuration  
`docker container port web1`  
`docker port web1`

> 80/tcp -> 0.0.0.0:8080

Get network configuration of container  
<small>Look for `NetworkSettings.IPAddress` or `NetworkSettings.Networks`</small>  
`docker container inspect web1`

or run below which will print IPAddress of the container  
`docker container inspect --format "{{ .NetworkSettings.IPAddress }}" web1`

> 172.17.0.2

## Docker Network

```
> docker network --help
Usage:  docker network COMMAND
Manage networks
Commands:
  connect     Connect a container to a network
  create      Create a network
  disconnect  Disconnect a container from a network
  inspect     Display detailed information on one or more networks
  ls          List networks
  prune       Remove all unused networks
  rm          Remove one or more networks

Run 'docker network COMMAND --help' for more information on a command.
```

List networks  
`docker network ls`

Create new network `XYZnet` (default to bridge network)  
`docker network create XYZnet`

Connect a new network to a container  
`docker network connect XYZnet web1`  
<small>web1 is a nginx container</small>

Disconnect `bridge` network from a container  
`docker network disconnect bridge web1`

Verify network information and see containers attached to `XYZnet`  
`docker network inspect XYZnet`

```
...
 "Containers": {
	"54e64e60f910136f91998db9d3f1d9045ca683d29ead95ada901a4c7e91e4288": {
		"Name": "web1",
		"EndpointID": "1d63c1b2e61312d80fe0fbbbee165ad52288066f54b44ca696959dd416b2d74b",
		"MacAddress": "02:42:ac:12:00:02",
		"IPv4Address": "172.18.0.2/16",
		"IPv6Address": ""
	},
	"c37a2c2bd5231a6f9c4fe90579532f4314d9185e482e821682ddad3955f4b25d": {
		"Name": "ub1",
		"EndpointID": "bd465a8cbc688cfeb1043cf20c626dbdbb5a04c26e7deaa9038eff70457dd5f7",
		"MacAddress": "02:42:ac:12:00:03",
		"IPv4Address": "172.18.0.3/16",
		"IPv6Address": ""
	}
},
...
```

Verify container has new network XYZnet detail  
`docker container inspect web1`

```
...
 "Networks": {
	"XYZnet": {
		"IPAMConfig": {},
		"Links": null,
		"Aliases": [
				"e91c8fc0daea"
		],
		"NetworkID": "3fdb608dcc4ef77babdfc22e2bd47682fe13c01ef2d06df5a935f32d8bfe3735",
		"EndpointID": "3ee6ebb3007f0505e525de527977b19798c1c129bbee51139259d52c568bb7a9",
		"Gateway": "172.18.0.1",
		"IPAddress": "172.18.0.2",
		"IPPrefixLen": 16,
		"IPv6Gateway": "",
		"GlobalIPv6Address": "",
		"GlobalIPv6PrefixLen": 0,
		"MacAddress": "02:42:ac:12:00:02",
		"DriverOpts": {}
	}
}
...
```

## Name resolution in bridge network

User-defined bridge network has automatic DNS resolution between containers. Default `bridge` network will not have DNS resolution. Read more in [here - docs.docker.com](https://docs.docker.com/network/bridge/#differences-between-user-defined-bridges-and-the-default-bridge)  

Create alpine container with name `sv1`, attach to network XYZnet, add network alias `superman`, and run with interactive terminal.  
`docker container run --name sv1 -it --network XYZnet --network-alias superman1 alpine sh`  
`docker container run --name sv2 -it --network XYZnet --network-alias superman2 alpine sh`  

With above setup, we can ping another container with container name or network alias.  
`ping sv1`  
`ping superman2`
