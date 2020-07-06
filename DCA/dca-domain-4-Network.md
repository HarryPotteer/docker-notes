# Domain 4: Networking (15% of exam)

- Describe the Container Network Model and how it interfaces with the Docker engine and network and IPAM drivers. [ref: DockerSuccessCenter - Networking](https://success.docker.com/article/networking/)
- Describe the different types and use cases for the built-in network drivers. [ref: Docker Docs - Network](https://docs.docker.com/network/) | [ref: Networking drivers use case](https://blog.docker.com/2016/12/understanding-docker-networking-drivers-use-cases/)
- Describe the types of traffic that flow between the Docker engine, registry and UCP controllers. [ref: DockerSuccessCenter - Networking](https://success.docker.com/article/networking/)
- Describe and demonstrate how to create a Docker bridge network for developers to use for their containers. [ref: Docker Docs - Network tutorial](https://docs.docker.com/network/network-tutorial-standalone/)
- Describe and demonstrate how to publish a port so that an application is accessible externally. [ref: Exposing ports](https://github.com/wsargent/docker-cheat-sheet#exposing-ports)
- [Identify which IP and port a container is externally accessible on.](https://docs.docker.com/engine/reference/commandline/port/#examples)
- Compare and contrast ["host"](https://docs.docker.com/engine/swarm/services/#publish-a-services-ports-directly-on-the-swarm-node) and ["ingress"](https://docs.docker.com/engine/swarm/ingress/) publishing modes.
- Describe and demonstrate how to configure Docker to use external DNS. [Docker Docs - DNS](https://docs.docker.com/config/containers/container-networking/#dns-services) | [add-host option](https://docs.docker.com/engine/reference/commandline/run/#add-entries-to-container-hosts-file---add-host) | [Sample custom DNS](https://gist.github.com/Evalle/7b21e0357c137875a03480428a7d6bf6)
- Describe and demonstrate how to use Docker to load balance HTTP/HTTPs traffic to an application (Configure L7 load balancing with Docker EE). [ref: Docker UCP - Load Balancer](https://docs.mirantis.com/docker-enterprise/v3.1/dockeree-products/ucp/ucp-configure/join-nodes/use-a-load-balancer.html) | [ref: DTR - Load Balancer](https://docs.mirantis.com/docker-enterprise/v3.1/dockeree-products/dtr/dtr-configure/use-a-load-balancer.html)
- ~~Understand and describe the types of traffic that flow between the Docker engine, registry, and UCP controllers~~ <small>(duplicate)</small>
- Describe and demonstrate how to deploy a service on a [Docker overlay network](https://docs.docker.com/network/overlay/)
- Describe and demonstrate how to [troubleshoot container and engine logs to resolve connectivity issues between containers.](https://success.docker.com/article/troubleshooting-container-networking)
- Describe how to route traffic to Kubernetes pods using ClusterIP and NodePort services.
- Describe the Kubertnetes’ container network model.
