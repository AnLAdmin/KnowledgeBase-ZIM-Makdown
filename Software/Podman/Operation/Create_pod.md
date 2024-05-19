# Create pod
Created Samstag 14 November 2020

[Src](http://docs.podman.io/en/latest/markdown/podman-pod-create.1.html)

Variables
---------
Pod name:	Name of the pod
Pod hostname:	<Pod name> or something else
Network:	Name of the podman network to bind the pod to.

Default
-------
# podman pod create network=<Network>,... --name=<Pod name> --p=<Host port>:<Container port>

