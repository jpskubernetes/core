# Pod

Pods are the fundamental unit of deployent. They represent a group of one or more container that are tightly coupled and shared storage (either persistent or ephemeral).

- A Pod is like a single container ship that holds one or more cargo containers (your application containers).
- These containers share resources and are co-located, meaning they run on the same node in the Kubernetes cluster.
- Each container within a Pod has its own process space and filesystem, but they can communicate and share data through mechanisms like volumes.

> Higher-level constructs like Deployments and ReplicaSets that manage Pod lifecycles.

> <kubectl get pods>, <kubectl describe pod [pod_name]>, and <kubectl logs [pod_name]> to list, inspect, and view logs of running Pods.

NOTE: 

As well as application containers, 
1. A Pod can contain init containers that run during Pod startup. 
2. Inject ephemeral containers for debugging a running Pod.

## Topic structure

- Workloads
    - Pods
        - Pod Lifecycle
        - Init Containers
        - Sidecar Containers
        - Ephemeral Containers
        - Disruptions
        - Pod Quality of Service Classes
        - User Namespaces
        - Downward API
    - Workload Management
        - Autoscaling Workloads
        - Managing Workloads