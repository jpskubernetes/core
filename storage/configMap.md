# Volumes and Mount

A volume is a directory that is accessible to containers in a pod. Volumes provide a way for containers to store and access data, and they can be used to share data between containers in the same pod.

![volumeMount](image.png)


```yaml
// pod.yaml
apiVersion: v1
kind: Pod
metadata:
  name: myapp
spec:
  containers:
    - name: myapp-container
      image: myapp-image
      volumeMounts:
        - name: data-volume
          mountPath: /data
  volumes:
    - name: data-volume
      hostPath:
        path: /mnt/data


```

![volume-mount-drawback](volume-mount-drawback.png)