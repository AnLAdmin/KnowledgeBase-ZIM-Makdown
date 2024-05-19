# Copy files
Created Montag 06 Juli 2020

Its posible to copy files from to containers. ([Src](https://docs.docker.com/engine/reference/commandline/cp/))

$ docker cp [OPTIONS] CONTAINER:SRC_PATH DEST_PATH
or
$ docker cp [OPTIONS] SRC_PATH|- CONTAINER:DEST_PATH

E.g.
$ docker cp nginx:/etc/nginx/nginx.conf /srv/container/nginx/data/etc/

