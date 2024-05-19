# Connect with client
Created Freitag 16 April 2021

Host
----

Podman
------

### By ip
$ podman exec -it --network=<Same as Redis instance> <image>:<image version>  redis-cli -h <Host name to Redis instance> -p <Port to Redis instance> --askpass

### By unix socket
# podman exec -it -v=<Path to unix socket directory>:/tmp <image>:<image version>  redis-cli -s <Path to unix socket> --user <Redis user> --askpass

