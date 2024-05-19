# Consideration
Created Samstag 18 Juli 2020

User ID outside and inside identical
------------------------------------
Set flag --userns=keep-id.
-> This is usefull if you specifiy an non root user (and group) ID at container startup like with gitea.
-> Or want that the ID of the host (login/container start) user is the same.

Limitations
-----------
[Shortcomings of Rootless Podman](https://github.com/containers/podman/blob/master/rootless.md)

