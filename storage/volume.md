# Volumes

On-disk files in a container are ephemeral, which presents some problems for non-trivial applications when running in containers. 

> One problem occurs when a container crashes or is stopped. Container state is not saved so all of the files that were created or modified during the lifetime of the container are lost.
<During a crash, kubelet restarts the container with a clean state.>

> Another problem occurs when multiple containers are running in a Pod and need to share files. 

<span style="color:red; font-weight:500">It can be challenging to setup and access a shared filesystem across all of the containers.</span>

## Important point

1. A Pod can use any number of volume types simultaneously. 
2. <Ephemeral volume> types have a lifetime of a pod, but <persistent volumes> exist beyond the lifetime of a pod. 


## Notes about volumes

- A pod can mount multiple volumes.
- A pod can mount multiple types of volume.
- A volume that is mounted on a pod can be shared among the containers in the pod.
- We recommend that you create persistent volumes (PVs) and PVCs to mount volumes in Kubernetes.
- We recommend that you do not mount an excess number of volumes on a pod.


### Kubernetes provides a wide variety of volume types. ACK supports the following commonly used volume types:

|Volume	| Description|
|--------|------------|
|Local storage	| You can mount local storage as volumes, such as HostPath and emptyDir volumes. These volumes store data on specific nodes of the cluster and do not drift with applications. The stored data becomes unavailable when the nodes are down.|
| Network storage	| You can mount network storage as volumes, such as Ceph, GlusterFS, NFS, and iSCSI volumes. These volumes store data by using remote storage services. When you use these volumes, you must mount the storage services locally.|
| Secrets and ConfigMaps |Secrets and ConfigMaps are special volumes that store the object information about a cluster. Object data is mounted as volumes to nodes for use by applications.|
|PVC | Persistent volume claims (PVCs) provide a mechanism for defining volumes. A PVC abstracts a volume into a pod-independent object. The storage information that is defined for or associated with this object is stored in a volume and mounted for use by Kubernetes workloads.|

> Note
Container Storage Interface (CSI) and FlexVolume are two extensions of volumes. Each extension can be divided into different StorageClasses.