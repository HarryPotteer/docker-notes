# Docker Certified Associate

`Version 1.3 May 2020` [^PDF^](https://docker.cdn.prismic.io/docker/4a619747-6889-48cd-8420-60f24a6a13ac_DCA_study+Guide_v1.3.pdf)

| Exam Domain                              | Percentage |
| ---------------------------------------- | ---------- |
| Orchestration                            | 25%        |
| Image Creation, Management, and Registry | 20%        |
| Installation and Configuration           | 15%        |
| Networking                               | 15%        |
| Security                                 | 10%        |
| Storage and Volumes                      | 10%        |

## Exam Domain

### Domain 1: Orchestration (25% of exam)

- [Complete the setup of a swarm mode cluster, with managers and worker nodes](https://docs.docker.com/engine/swarm/swarm-tutorial/create-swarm/)
- [Describe and demonstrate how to extend the instructions to run individual containers into running services under swarm](https://docs.docker.com/engine/swarm/swarm-tutorial/deploy-service/)
- Describe the importance of quorum in a swarm cluster.
  [^1^ admin-guide](https://docs.docker.com/engine/swarm/admin_guide/) | [^2^ raft](https://docs.docker.com/engine/swarm/raft/) | [^3^ medium](https://medium.com/@kasunmaduraeng/importance-of-quorum-in-a-swarm-cluster-c67ae9bb2d6f)
- [Describe the difference between running a container and running a service.](https://docs.docker.com/engine/swarm/how-swarm-mode-works/services/#services-tasks-and-containers)
- [Interpret the output of `docker inspect` commands](https://docs.docker.com/engine/swarm/swarm-tutorial/inspect-service/)
- [Convert an application deployment into a stack file using a YAML compose file with `docker stack deploy`](https://docs.docker.com/engine/swarm/stack-deploy/)
- [Manipulate a running stack of services](https://docs.docker.com/engine/reference/commandline/stack_services/#related-commands)
- [Describe and demonstrate orchestration activities](https://docs.docker.com/get-started/orchestration/)
- [Increase number of replicas](https://docs.docker.com/engine/reference/commandline/service_scale/)
- [Add networks, publish ports](https://docs.docker.com/network/)
- [Mount volumes](https://docs.docker.com/storage/volumes/)
- [Describe and demonstrate how to run replicated and global services](https://docs.docker.com/engine/swarm/how-swarm-mode-works/services/#replicated-and-global-services)
- [Apply node labels to demonstrate placement of tasks](https://success.docker.com/article/using-contraints-and-labels-to-control-the-placement-of-containers)
- [Describe and demonstrate how to use templates with `docker service create`](https://docs.docker.com/engine/reference/commandline/service_create/#create-services-using-templates)
- [Identify the steps needed to troubleshoot a service not deploying](https://success.docker.com/article/swarm-troubleshooting-methodology)
- [Describe how a Dockerized application communicates with legacy systems](https://docs.docker.com/config/containers/container-networking/)
- [Describe how to deploy containerized workloads as Kubernetes pods and deployments](https://docs.docker.com/get-started/kube-deploy/)
- [Describe how to provide configuration to Kubernetes pods using configMaps and secrets](https://opensource.com/article/19/6/introduction-kubernetes-secrets-and-configmaps)

### Domain 2: Image Creation, Management, and Registry (20% of exam)

- [Describe the use of Dockerfile](https://docs.docker.com/engine/reference/builder/)
- [Describe options, such as add, copy, volumes, expose, entry point](https://docs.docker.com/engine/reference/builder/#from)
- [Identify and display the main parts of a Dockerfile](https://docs.docker.com/engine/reference/builder/#dockerfile-examples)
- [Describe and demonstrate how to create an efficient image via a Dockerfile](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
- [Describe and demonstrate how to use CLI commands to manage images, such as list, delete, prune, rmi](https://docs.docker.com/engine/reference/commandline/image/#usage)
- [Describe and demonstrate how to inspect images and report specific attributes using filter and format](https://docs.docker.com/engine/reference/commandline/images/#filtering)
- [Describe and demonstrate how to tag an image.](https://docs.docker.com/engine/reference/commandline/tag/)
- [Describe and demonstrate how to apply a file to create a Docker image](https://docs.docker.com/engine/reference/commandline/image_load/)
- [Describe and demonstrate how to display layers of a Docker image](https://docs.docker.com/engine/reference/commandline/image_inspect/)
- Describe and demonstrate how to modify an image to a single layer ([multi-stage build](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#minimize-the-number-of-layers), [single layer](https://stackoverflow.com/questions/39695031/how-make-docker-layer-to-single-layer))
- [Describe and demonstrate registry functions](https://docs.docker.com/registry/)
- [Deploy a registry](https://docs.docker.com/registry/deploying/)
- [Log into a registry](https://docs.docker.com/engine/reference/commandline/login/)
- [Utilize search in a registry](https://docs.docker.com/engine/reference/commandline/search/)
- [Push an image to a registry](https://docs.docker.com/engine/reference/commandline/push/)
- [Sign an image in a registry](https://docs.docker.com/engine/reference/commandline/trust_sign/)
- [Pull](https://docs.docker.com/engine/reference/commandline/pull/) and [delete](https://docs.docker.com/registry/spec/api/#deleting-an-image) images from a registry

### Domain 3: Installation and Configuration (15% of exam)

- Describe [sizing requirements for installation.](https://docs.docker.com/datacenter/ucp/2.2/guides/admin/install/system-requirements/#hardware-and-software-requirements)
- Describe and demonstrate the [setup of repo, selection of a storage driver, and installation of the Docker engine on multiple platforms.](https://docs.docker.com/install/)
  [^1^ Upgrade the Docker engine](https://docs.docker.com/install/linux/docker-ce/ubuntu/#upgrade-docker-engine---community)

- Describe and demonstrate [configuration of logging drivers (splunk, journald, etc).](https://docs.docker.com/config/containers/logging/configure/)
- Describe and demonstrate how to [set up swarm, configure managers, add nodes, and setup backup schedule.](https://docs.docker.com/engine/swarm/admin_guide/)
- Describe and demonstrate how to [create and manage user and teams.](https://docs.docker.com/datacenter/dtr/2.4/guides/admin/manage-users/create-and-manage-teams/)
- Describe and demonstrate how to [configure the Docker daemon to start on boot.](https://docs.docker.com/install/linux/linux-postinstall/)
- Describe and demonstrate how to [use certificate-based client-server authentication to ensure a Docker daemon has the rights to access images on a registry.](https://docs.docker.com/engine/security/certificates/)
- Describe the use of [namespaces, cgroups, and certificate configuration.](https://docs.docker.com/engine/docker-overview/#namespaces)
- Describe and interpret errors to [troubleshoot installation issues without assistance.](https://docs.docker.com/config/daemon/#troubleshoot-the-daemon)
- Describe and demonstrate the steps to deploy the Docker engine, UCP, and DTR on AWS and on-premises in an HA configuration.
  [Docker engine](https://docs.docker.com/install) |
  [Docker Enterprise docs](https://docs.mirantis.com/docker-enterprise/v3.1/) |
  [DTR 2.1](https://docs.mirantis.com/docker-enterprise/v2.1/dockeree-products/dtr.html) |
  [DTR 3.1](https://docs.mirantis.com/docker-enterprise/v3.1/dockeree-products/dtr.html) |
  [UCP 3.1](https://docs.mirantis.com/docker-enterprise/v3.1/dockeree-products/ucp.html) |
  [Docker Engine Enterprise](https://docs.mirantis.com/docker-enterprise/v3.1/dockeree-products/docker-engine-enterprise.html) |
  [Fault tolerance](https://docs.docker.com/engine/swarm/admin_guide/#add-manager-nodes-for-fault-tolerance) |
  [Docker on AWS](https://aws.amazon.com/docker/)
- Describe and demonstrate how to [configure backups for UCP and DTR.](https://docs.docker.com/datacenter/ucp/2.2/guides/admin/backups-and-disaster-recovery/)

### Domain 4: Networking (15% of exam)

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

### Domain 5: Security (15% of exam)

- Describe security administration and tasks. [ref: Docker Docs](https://docs.docker.com/engine/security/security/) | [ref: Docker EE - Security and access control](https://docs.mirantis.com/docker-enterprise/v3.1/dockeree-products/dee-intro/sec-and-access.html)
- [Describe the process of signing an image.](https://docs.docker.com/engine/security/trust/content_trust/#signing-images-with-docker-content-trust)
- Describe default engine security. [ref: default engine security](https://docs.docker.com/engine/security/security/)
- Describe swarm default security. [ref: swarm default security](https://docs.docker.com/engine/swarm/how-swarm-mode-works/pki/)
- Describe MTLS. [ref MLTS](https://diogomonica.com/2017/01/11/hitless-tls-certificate-rotation-in-go/)
- Describe identity roles. [ref: UCP Identity roles](https://docs.docker.com/datacenter/ucp/2.2/guides/access-control/permission-levels/#roles)
- Compare and contrast UCP workers and managers. [ref: UCP Architecture](https://docs.docker.com/datacenter/ucp/2.2/guides/architecture/)
- Describe the process to use external certificates with UCP and DTR. (**UCP** [from cli](https://success.docker.com/article/how-do-i-provide-an-externally-generated-security-certificate-during-the-ucp-command-line-installation), [from GUI](https://docs.docker.com/ee/ucp/admin/configure/use-your-own-tls-certificates/#configure-ucp-to-use-your-own-tls-certificates-and-keys), [print the public certificates](https://docs.docker.com/datacenter/ucp/3.0/reference/cli/dump-certs/)), [**DTR**](https://docs.docker.com/ee/dtr/admin/configure/use-your-own-tls-certificates/))
- Describe and demonstrate that an image passes a security scan. [ref: Image passes a security scan](https://docs.docker.com/datacenter/dtr/2.5/guides/admin/configure/set-up-vulnerability-scans/)
- Describe and demonstrate how to enable Docker Content Trust. [ref: Docker Content Trust](https://docs.docker.com/engine/security/trust/content_trust/)
- Describe and demonstrate how to configure RBAC with UCP. [ref: UCP - Authorize role-based access](https://docs.mirantis.com/docker-enterprise/v3.1/dockeree-products/ucp/authorize.html)
- Describe and demonstrate how to integrate UCP with LDAP/AD. [ref: UCP - Create teams with LDAP](https://docs.mirantis.com/docker-enterprise/v3.1/dockeree-products/ucp/authorize/create-with-ldap.html)
- Describe and demonstrate how to create UCP client bundles. [ref: UCP client bundles](https://www.docker.com/blog/get-familiar-docker-enterprise-edition-client-bundles/) | [ref: UCP user access](https://docs.mirantis.com/docker-enterprise/v3.1/dockeree-products/ucp/user-access.html) | [ref: download client bundle from command line](https://success.docker.com/article/download-client-bundle-from-the-cli)

### Domain 6: Storage and Volumes (10% of exam)

- Identify the correct graph drivers to uses with various operating systems. [ref: Storage drivers](https://docs.docker.com/storage/storagedriver/select-storage-driver/) | [ref: graphdriver plugins](https://docs.docker.com/engine/extend/plugins_graphdriver/)
- Describe and demonstrate how to configure devicemapper. [ref: devicemapper](https://docs.docker.com/storage/storagedriver/device-mapper-driver/)
- Compare and contrast object and block storage and when they should be used. [ref: block storage, object storage](https://rancher.com/block-object-file-storage-containers/)
- Describe how an application is composed of layers and where these layers reside on the filesystem. [ref: images and layers](https://docs.docker.com/storage/storagedriver/#images-and-layers)
- Describe the use of volumes are used with Docker for persistent storage. [ref: volumes](https://docs.docker.com/storage/volumes/)
- Identify the steps to take to clean up unused images on a filesystem and DTR. [ref: image prune](https://docs.docker.com/engine/reference/commandline/image_prune/) | [ref: system prune](https://docs.docker.com/engine/reference/commandline/system_prune/) | [ref: delete from DTR](https://docs.docker.com/ee/dtr/user/manage-images/delete-images/))
- Describe and demonstrate how storage can be used across cluster nodes. [ref: volume plugins](https://docs.docker.com/engine/extend/legacy_plugins/#volume-plugins) | [ref: Docker volume plugins](https://docs.docker.com/engine/extend/plugins_volume/)
- Describe how to provision persistent storage to a Kubernetes pod using persistentVolumes. [ref: Persistent Volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) | [ref: Persistent Kubernetes Storage](https://docs.mirantis.com/docker-enterprise/v3.0/dockeree-products/ucp/deploy-apps-with-kubernetes/persistent-storage.html)
- Describe the relationship between container storage interface drivers, storageClass, persistentVolumeClaim and volume objects in Kubernetes. [ref: CSI drivers](https://docs.mirantis.com/docker-enterprise/v3.1/dockeree-products/ucp/deploy-apps-with-kubernetes/persistent-storage/using-csi-drivers.html)

https://success.docker.com/article/an-introduction-to-storage-solutions-for-docker-enterprise

## Exam Details

- 13 multiple choice and 42 discrete option multiple choice (DOMC) questions in 90 minutes
- Designed to validate professionals with a minimum of 6 to 12 months of Docker experience
- Remotely proctored on your Windows or Mac computer
- Available globally in English
- USD \$195 or Euro €175 purchased online
- Results delivered immediately
- 2 years validity

## What is DOMC discrete option multiple choice?

- DOMC represents a relatively simple but very useful change in the delivery of multiple choice question.
- Instead of showing all of the options at one time, as is usually done, options are randomly presented one at a time.
- For each presented option, the test taker chooses YES or NO indicating whether the he or she thinks it is the correct one.
- When the question is answered correctly or incorrectly, no more options appear, and the next question is presented.

## Introduction about DCA

This examination is based upon critical job activities a Docker Certified Associate performs. The skills and knowledge certified by this examination represent a level of expertise where a certified Docker Associate can:

- Run containerized applications from pre-existing images stored in a centralized registry
- Deploy images across the cluster
- Triage and resolve issue reports from stakeholders and resolve
- Standup up on Enterprise clusters with one UCP manager, one DTR replica, and one worker node
- Migrate traditional applications to containers
- Configure and troubleshoot Docker engine
- Perform general maintenance and configuration

Candidates for this certification should have at least six months to one year of experience with Docker, including exposure to the Docker Enterprise Edition. The knowledge, skills and experience required at this level should also include:

- container security
- experience with at least one cloud provider
- configuration management tools
- Linux and/or Windows Server

The skills and knowledge this examination measures are derived from an understanding of the jobs of current Docker users. A team of highly qualified Docker experts defined the test content and developed the test items.
Note: This examination blueprint includes weighting, test objectives, and example content. Example topics and concepts are included to clarify the test objectives; they should not be construed as a comprehensive listing of all the content of this examination.

## Credits and Links

- Links are mostly from [Evalle DCA @ Github](https://github.com/Evalle/DCA)
- [Docker Certification](https://success.docker.com/certification)
- [DOMC discrete option multiple choice](http://trydomc.com/about)
- [Book Certification Exam](https://prod.examity.com/docker/)
- [Docker EE docs](https://docs.mirantis.com/docker-enterprise/v3.1/) | [single-page](https://docs.mirantis.com/docker-enterprise/v3.1/dockeree-products/single/index.html)
- [Docker Enterprise Reference Architectures](https://docs.mirantis.com/docker-enterprise/v3.1/dockeree-ref-arch/index.html)
- [Older DCA references](https://github.com/suryaval/docker-certified-associate)
- [Docker Cheat Sheet](https://github.com/wsargent/docker-cheat-sheet)
