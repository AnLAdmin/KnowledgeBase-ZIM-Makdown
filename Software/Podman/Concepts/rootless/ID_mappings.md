# ID mappings
Created Samstag 18 Juli 2020

[Sets](../../../Linux/Security/User/Concepts/Mapping/Create.md) user and group ID mappings inside a container for a user who runs containers.

Execute the following command after the change:
# podman system migrate

Reason
------
For these changes to be propagated, it is necessary to first stop all running containers associated with the user and to also stop the pause process and delete its pid file. 

