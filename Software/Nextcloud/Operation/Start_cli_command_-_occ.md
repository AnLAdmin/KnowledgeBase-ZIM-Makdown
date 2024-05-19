# Start cli command - occ
Created Sonntag 06 Juni 2021

Manual:	[OCC command](https://docs.nextcloud.com/server/latest/admin_manual/configuration_server/occ_command.html#http-user-label)

Variables
---------

Username:	Nextcloud user. On Debian/Ubuntu it is **www-data**.
Container:	Name/ID of the container.

Host
----
# sudo -u <Username> php occ

Podman
------
# podman exec --user <Username> <Container> php occ

