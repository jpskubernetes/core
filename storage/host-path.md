# Use hostPath volumes

1. A hostPath volume mounts a file or directory from the file system of the host node to a pod. 
2. This topic describes how to mount hostPath volumes to pods.

## Volume mount modes
hostPath volumes can be mounted in the following modes:

| Volume mount mode |	Description |
|------------------|------------|
|DirectoryOrCreate | In this mode, if no content is found in the specified path, an empty directory is created on demand. The permission on the created directory is set to 0755. The directory has the same group and ownership with kubelet.|
| Directory | Therefore, a directory must exist in the specified path.|
|FileOrCreate |	In this mode, if no content is found in the specified path, an empty file is created. The permission of the created file is set to 0644. The file has the same group and ownership with kubelet.|
|File |	In this mode, a file must exist in the specified path.|

```yaml

# Use the following template to directly mount a hostPath volume to a pod:

apiVersion: v1
kind: Pod
metadata:
  name: test
spec:
  containers:
  - image: nginx:1.7.9
    name: test
    volumeMounts:
    - mountPath: /test
      name: test-volume
  volumes:
  - name: test-volume
    hostPath:
      path: /data
      type: DirectoryOrCreate

```