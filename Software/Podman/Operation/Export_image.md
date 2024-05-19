# Export image
Created Freitag 17 September 2021

Export (save) image from the local repository.

As OCI archive
--------------
# podman save --format oci-archive -o <Path to storage archive> <Image name>:<Image tag/version>

### E.g.
# podman save --format oci-archive -o /srv/container/@nextcloud/backup/images/nextcloud_supervisord_22.1.1.tar nextcloud_supervisord:22.1.1

