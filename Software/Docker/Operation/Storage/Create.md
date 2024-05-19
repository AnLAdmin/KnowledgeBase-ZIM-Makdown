# Create
Created Dienstag 23 Juni 2020

Volumes
-------

Bind mount
----------
Binds a directory located on the host into a container.
$ docker run -d \
  -it \
  --name <container name> \
  --mount type=bind,source=<path on host>,target=<path in container> \
  <image>

### E.g
$ docker run -d \
  -it \
  --name Gitea \
  --mount type=bind,source=/srv/gitea/data,target=/data \
  gitea/gitea:latest

tmpfs
-----

