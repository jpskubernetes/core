# Ephemeral Volumes

Ephemeral volumes are designed for these use cases. Because volumes follow the Pod's lifetime and get created and deleted along with the Pod, Pods can be stopped and restarted without being limited to where some persistent volume is available.

> Note: <CSI> - Container Storage Interface, its defines a standard  storage interface to expose storage system to container.

> Because volumes follow the Pod's lifetime and get created and deleted along with the Pod, Pods can be stopped and restarted without being limited to where some persistent volume is available.

> Ephemeral volumes are specified inline in the Pod spec, which simplifies application deployment and management.

## Types of ephemeral volumes

Kubernetes supports several different kinds of ephemeral volumes for different purposes:

- emptyDir: empty at Pod startup, with storage coming locally from the kubelet base directory (usually the root disk) or RAM
- configMap, downwardAPI, secret: inject different kinds of Kubernetes data into a Pod
- CSI ephemeral volumes: similar to the previous volume kinds, but provided by special CSI drivers which specifically support this feature

generic ephemeral volumes, which can be provided by all storage drivers that also support persistent volumes <emptyDir>, <configMap>, <downwardAPI>, <secret> are provided as local ephemeral storage. They are managed by kubelet on each node.

> CSI ephemeral volumes must be provided by third-party CSI storage drivers.

Generic ephemeral volumes can be provided by third-party CSI storage drivers, but also by any other storage driver that supports dynamic provisioning. 

Some CSI drivers are written specifically for CSI ephemeral volumes and do not support dynamic provisioning: those then cannot be used for generic ephemeral volumes.