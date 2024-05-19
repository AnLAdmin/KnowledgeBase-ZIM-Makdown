# Rootless
Created Freitag 17 Juli 2020

[Source](https://github.com/containers/fuse-overlayfs)

20.04
-----
[Install](../Ubuntu.md) podman with recommanded packages.
[Install](../../../fuse-overlayfs/Installation/Ubuntu.md) fuse-overlay.

Change container runtime in ~/.config/containers/containers.conf:
Uncomment **# runtime = "runc"** and change to *crun*.
```ini
# Default OCI runtime
#
# runtime = "runc"
runtime = "crun"
```

OPTIONAL: If you want to use *podman stats *add the following to your kernel command line in **/etc/default/grub**:
```js
GRUB_CMDLINE_LINUX_DEFAULT="... systemd.unified_cgroup_hierarchy=1 ..."
```

# update-grub
....

18.04
-----
[Install](../Ubuntu.md) podman with recommanded packages.
[Install](../../../fuse-overlayfs/Installation/Ubuntu.md) fuse-overlay.

Change container runtime in ~/.config/containers/containers.conf:
Uncomment **# runtime = "runc"** and change to *crun*.
```ini
# Default OCI runtime
#
runtime = "crun"
```


OPTIONAL: If ping in the container is required change access to ping for unpriviliged users in **/etc/sysctl.d/60-*.conf**:
```ini
net.ipv4.ping_group_range=0 <MAX_GID>
```

MAX_GID: Max group id which can send pings.

OPTIONAL: Default is 1380 (on Ubuntu 18.04). Set the number of user namespaces to <max number of namespaces> per user in **/etc/sysctl.d/60-*.conf**:
```ini
user.max_user_namespaces=<max number of namespaces>
```


Create container user (default: commander is set during installation):

* ☐ Is container user the right way or does it need a user per container? @todo @podman

# useradd -c "<user's full name>" -s /bin/bash -m <container user name>
[Set](../../Concepts/rootless/ID_mappings.md) /etc/subuid and /etc/subgid for container user.


* ☐ Podman: Finish rootless installation @todo @podman
	* ☐ fuse-overlayfs static binary not working -> [Build](https://github.com/containers/fuse-overlayfs) own static binary.


