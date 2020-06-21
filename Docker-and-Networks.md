---
title: Docker-and-Networks
created: '2020-06-21T06:27:09.330Z'
modified: '2020-06-21T08:23:03.846Z'
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

Create new network `XYZ-net`  
`docker network create XYZ-net`  

Connect a new network to a container  
`docker network connect XYZ-net web1`  
<small>web1 is a nginx container</small>  

Disconnect `bridge` network from a container  
`docker network disconnect bridge web1`  

Verify network information and see containers attached to `XYZ-net`  
`docker network inspect XYZ-net`  

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

Verify container has new network XYZ-net detail  
`docker container inspect web1`  

```
...
	"NetworkSettings": {
		"Bridge": "",
		"SandboxID": "b75efb56416abffd5ff89fd3c651722af1e735c9c47519ee3e69fad886bcbbae",
		"HairpinMode": false,
		"LinkLocalIPv6Address": "",
		"LinkLocalIPv6PrefixLen": 0,
		"Ports": {},
		"SandboxKey": "/var/run/docker/netns/b75efb56416a",
		"SecondaryIPAddresses": null,
		"SecondaryIPv6Addresses": null,
		"EndpointID": "73b9ad47cc8cb61872cf752e239469c3792e1a871615e56fe012e9b2e3d7eb71",
		"Gateway": "172.17.0.1",
		"GlobalIPv6Address": "",
		"GlobalIPv6PrefixLen": 0,
		"IPAddress": "172.17.0.2",
		"IPPrefixLen": 16,
		"IPv6Gateway": "",
		"MacAddress": "02:42:ac:11:00:02",
		"Networks": {
			"XYZ-net": {
				"IPAMConfig": {},
				"Links": null,
				"Aliases": [
					"c37a2c2bd523"
				],
				"NetworkID": "3fedbdf5a44fda23ccef6e69a9f97ce8ef280c6bbeb76ffdfa1ddfc5a154a04b",
				"EndpointID": "bd465a8cbc688cfeb1043cf20c626dbdbb5a04c26e7deaa9038eff70457dd5f7",
				"Gateway": "172.18.0.1",
				"IPAddress": "172.18.0.3",
				"IPPrefixLen": 16,
				"IPv6Gateway": "",
				"GlobalIPv6Address": "",
				"GlobalIPv6PrefixLen": 0,
				"MacAddress": "02:42:ac:12:00:03",
				"DriverOpts": {}
			},
			"bridge": {
				"IPAMConfig": null,
				"Links": null,
				"Aliases": null,
				"NetworkID": "9b1120f1a544e7ec3787711d7b6565d0e36355a7306510d7d08bc3d2614afd6d",
				"EndpointID": "73b9ad47cc8cb61872cf752e239469c3792e1a871615e56fe012e9b2e3d7eb71",
				"Gateway": "172.17.0.1",
				"IPAddress": "172.17.0.2",
				"IPPrefixLen": 16,
				"IPv6Gateway": "",
				"GlobalIPv6Address": "",
				"GlobalIPv6PrefixLen": 0,
				"MacAddress": "02:42:ac:11:00:02",
				"DriverOpts": null
			}
		}
	}
...
```




