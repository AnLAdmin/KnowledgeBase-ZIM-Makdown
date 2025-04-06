# Create VM
Created Freitag 06 Dezember 2024

([Src](https://linuxcontainers.org/incus/docs/main/howto/instances_create/))

Create a vm
-----------
Creates a vm with a default concfiguration.
``$ incus init <VM name> --empty --vm``

Default root disk size is 10 GiB.
### Example
``$ incus init vmWin11 --empty --vm``

Create a vm with custom hw
--------------------------
``$ incus init <VM name> --empty --vm -c <``[``Instance options``](https://linuxcontainers.org/incus/docs/main/reference/instance_options/#instance-options)``> [-c ...] -d <``[``Device config``](https://linuxcontainers.org/incus/docs/main/reference/devices/)``> [-d ...]``

### Example
2 CPUs, 4 GiB of memory and 50 GiB of storage
``$ incus init vmWin11 --empty --vm -c limits.cpu=2 -c limits.memory=4GiB -d root,size=50GiB``

