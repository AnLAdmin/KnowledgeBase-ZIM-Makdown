# Download container image
Created Montag 06 September 2021

Download/pull container image from the container image repository like [Docker Hub](https://hub.docker.com/) or [quay.io](https://quay.io/).
[Src](https://docs.podman.io/en/latest/markdown/podman-pull.1.html)

### Note
There is a download limit (pull rate limit): 100 Downloads per 6h

Anonymous
---------
Witout account
$ podman pull <Repository>/<Image name>:<tag>
E.g. $ podman pull docker.io/nextcloud:21.0.4

with account
------------
$ podman pull <Repository>/<username>/<Image name>:<tag>

