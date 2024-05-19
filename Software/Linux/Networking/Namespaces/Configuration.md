# Configuration
Created Samstag 18 Juli 2020

Maximum number of namespaces per user
-------------------------------------
Get the current value:
$ cat /proc/sys/user/max_user_namespaces
Set it temporary:
# sysctl user.max_user_namespaces=<number>
Set it permanently in **/etc/sysctl.conf**:
```ini
user.max_user_namespaces=<number>
```
 

