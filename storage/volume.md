# Volumes

On-disk files in a container are ephemeral, which presents some problems for non-trivial applications when running in containers. 

> One problem occurs when a container crashes or is stopped. Container state is not saved so all of the files that were created or modified during the lifetime of the container are lost.
<During a crash, kubelet restarts the container with a clean state.>

> Another problem occurs when multiple containers are running in a Pod and need to share files. 

<span style="color:red; font-weight:500">It can be challenging to setup and access a shared filesystem across all of the containers.</span>