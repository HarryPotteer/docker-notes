# Domain 6: Storage and Volumes (10% of exam)

- Identify the correct graph drivers to uses with various operating systems. [ref: Storage drivers](https://docs.docker.com/storage/storagedriver/select-storage-driver/) | [ref: graphdriver plugins](https://docs.docker.com/engine/extend/plugins_graphdriver/)
- Describe and demonstrate how to configure devicemapper. [ref: devicemapper](https://docs.docker.com/storage/storagedriver/device-mapper-driver/)
- Compare and contrast object and block storage and when they should be used. [ref: block storage, object storage](https://rancher.com/block-object-file-storage-containers/)
- Describe how an application is composed of layers and where these layers reside on the filesystem. [ref: images and layers](https://docs.docker.com/storage/storagedriver/#images-and-layers)
- Describe the use of volumes are used with Docker for persistent storage. [ref: volumes](https://docs.docker.com/storage/volumes/)
- Identify the steps to take to clean up unused images on a filesystem and DTR. [ref: image prune](https://docs.docker.com/engine/reference/commandline/image_prune/) | [ref: system prune](https://docs.docker.com/engine/reference/commandline/system_prune/) | [ref: delete from DTR](https://docs.docker.com/ee/dtr/user/manage-images/delete-images/))
- Describe and demonstrate how storage can be used across cluster nodes. [ref: volume plugins](https://docs.docker.com/engine/extend/legacy_plugins/#volume-plugins) | [ref: Docker volume plugins](https://docs.docker.com/engine/extend/plugins_volume/)
- Describe how to provision persistent storage to a Kubernetes pod using persistentVolumes. [ref: Persistent Volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) | [ref: Persistent Kubernetes Storage](https://docs.mirantis.com/docker-enterprise/v3.0/dockeree-products/ucp/deploy-apps-with-kubernetes/persistent-storage.html)
- Describe the relationship between container storage interface drivers, storageClass, persistentVolumeClaim and volume objects in Kubernetes. [ref: CSI drivers](https://docs.mirantis.com/docker-enterprise/v3.1/dockeree-products/ucp/deploy-apps-with-kubernetes/persistent-storage/using-csi-drivers.html)

https://docs.mirantis.com/docker-enterprise/v3.1/dockeree-ref-arch/storage/intro-to-storage.html
https://success.docker.com/article/an-introduction-to-storage-solutions-for-docker-enterprise
