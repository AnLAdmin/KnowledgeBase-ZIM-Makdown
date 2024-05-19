# Create
Created Dienstag 23 Juni 2020

Default
-------
# groupadd <group name>

System
------
Group for system users.
# groupadd -r <group name> [-g <group id>]

### specific system
E.g. container
# groupadd -K SYS_GID_MIN=<new start>  -K SYS_GID_MAX=<new end> -r <group name>
-K: Overwrites the defaults in /etc/login.defs.

