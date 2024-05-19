# Reload configuration
Created Montag 06 Juli 2020

Variables
---------
Container cli:		podman, docker
Container name:		NGINX Name of the container

Running native
--------------

### variant 1
# nginx -s reload

### variant 2
# service nginx force-reload

Running in a container
----------------------

### variant 1
<Container cli> exec -it <Container name> nginx -s reload
E.g.:
podman exec -it nginx nginx -s reload

### variant 2
# <Container cli> exec -it <Container name> /usr/sbin/service nginx force-reload
E.g.:
# podman exec -it nginx /usr/sbin/service nginx force-reload

