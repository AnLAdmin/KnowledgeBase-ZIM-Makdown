# Runtime
Created Freitag 03 Januar 2020

Low level runtime / runtime
---------------------------
Also kown as *low-level container runtimes*.
A container runtime starts containers. 
What they do:

* Create cgroup
* Run command(s) in cgroup
* Unshare to move to its own namespaces
* Clean up cgroup after command completes (namespaces are deleted automatically when not referenced by a running process)


List of some runtimes:

* runc
* lxc (not the lxd control tool)
* rkt (is more)
* lmctfy


High level runtime
------------------
Outsource container start to low level runtime. In my opinion they should be called something like *container manager*.
The manage container image repositories, images, and low level runtimes. The help build images.
List of some runtimes:

* Cri-O
* containerd
* rkt
* lxd
* [Docker](../../../Software/Docker.md)
* Podman


Container Runtime Interface (CRI)
---------------------------------
[Infos](https://github.com/kubernetes/community/blob/master/contributors/devel/sig-node/container-runtime-interface.md)
Interface between Kubernetes (or other container cluster / node manager) and high level runtimes.

