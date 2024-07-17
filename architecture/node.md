# Node

- kubernetes runs workload on nodes.
- It is virtual or physical machine.
- Control by conrol plane 

## components

1. kubelet
2. container runtime (CRI)
3. kube-proxy

# Management

There are two main ways tmo have added to the <API Server>:
1. The <kubelet> on node self-registers to the control panel.
2. Manually add a Node object.