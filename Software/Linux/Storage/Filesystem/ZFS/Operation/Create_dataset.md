# Create dataset
Created Sonntag 03 November 2024

Create a dataset mounted to /<Pool name>/<Dataset name>
``# zfs create <Pool name>/<Dataset name>[/<Dataset name>]``

Child datasets are mounted bellow there parents if not mountpoint property is given.
### Example
Create a dataset **mydataset** to pool **mypool** mounted to **/mypool/mydataset**.
``# zfs create mypool/mydataset``
Create a dataset **mydataset** to pool **mypool** mounted to **/mypool/mydataset**.

Customize mountpoint
--------------------
Create a dataset mounted to <Mount point>.
``# zfs create -o mountpoint=<Mountpoint> <Pool name>/<Dataset name>``
### Example
Create a dataset **mydataset** to pool **mypool** mounted to **/mnt/Music**.
``# zfs create -o mountpoint=/mnt/Music mypool/mydataset``

