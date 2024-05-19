# Create volume
Created Donnerstag 23 Juni 2022

Create a container specific volume at the podman default location.

Create a volume with ...
------------------------

### A**utomatically create name**
$ podman volume create

### S**elf defined name**
$ podman volume create MyName

### S**pecific filesystem**
$ podman volume create MyVolume --opt/-o device=tmpfs

### Specific user rights
$ podman volume create MyVolume --opt/-o o=uid=<User ID>,gid=<Group ID>

E.g. Set root user/group
$ podman volume create MyVolume --opt/-o o=uid=1000,gid=1000

