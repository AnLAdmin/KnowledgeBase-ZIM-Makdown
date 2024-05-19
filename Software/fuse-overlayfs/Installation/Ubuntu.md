# Ubuntu
Created Samstag 18 Juli 2020


20.14
-----
# apt install fuse-overlayfs

18.04
-----
Download fuse-overlay static binary for x86 (only available in Ubuntu repo >=20.04):
# wget <https://github.com/containers/fuse-overlayfs/releases/download/v1.1.2/fuse-overlayfs-x86_64>
Make is executable:
# chmod 0775 ./fuse-overlayfs-x86_64
Move binary:
# mv ./fuse-overlayfs-x86_64 /usr/bin/fuse-overlayfs



