# Create pool
Created Sonntag 27 Oktober 2024

A pool is created with the first [VDEV.](../../../../../../Glossary/ZFS/VDEV.md)
While creating a pool a root dataset is created with the same name as the pool and automatically mounted. Default mount point is /<Pool name>.
**Root dataset name CAN NOT be changed.**

Simple
------
Create a pool with one disk.
``# zpool create <Pool name> <Device>``
Pool name	Name of pool
Must begin with  a  letter,  and  can  only  contain  alphanumeric characters  as  well as underscore ("_"), dash ("-"), and period (".").

### Examlpe
``# zpool create mypool /dev/sda``
``# zpool create mypool sda``

Multiple (RAID 0)
-----------------
Create a pool with multiple disk. By default this creates a striped [VDEV](../../../../../../Glossary/ZFS/VDEV.md) (RAID 0).
``# zpool create <Pool name> <Device 1> <Device 2> ...``
### Examlpe
``# zpool create mypool /dev/sda /dev/sdb``
``# zpool create mypool sda sdb``

Mirror (RAID 1)
---------------
Create a pool with a mirrored [VDEV.](../../../../../../Glossary/ZFS/VDEV.md) A mirror can include more than 2 devices.
``# zpool create <Pool name> mirror <Device 1> <Device 2>``
### Examlpe
``# zpool create mypool mirror sda sdb``

Mirror (RAID 1) with more than 2 disks
--------------------------------------
Creating a mirror with more than 2 disks is possibe in that you create an additional mirror (with one disk).
``# zpool create <Pool name> mirror <Device 1> <Device 2> mirror <Device 3>``

Repeat the step for more disks.
**zpool status** will show a mirror [VDEV](../../../../../../Glossary/ZFS/VDEV.md) per additional disk.
### Examlpe
``# zpool add mypool mirror sda sdb mirror sdc``
In this case zool status will show two mirror [VDEVs.](../../../../../../Glossary/ZFS/VDEV.md)
  ``pool: mypool``
 ``state: ONLINE``
  ``scan: none requested``
``config:``

``NAME        STATE     READ WRITE CKSUM``
``mypool      ONLINE      0     0     0``
  ``mirror-0  ONLINE      0     0     0``
``/dev/sda  ONLINE     0     0     0``
``/dev/sdb  ONLINE     0     0     0``
  ``mirror-1  ONLINE      0     0     0``
``/dev/sdc  ONLINE     0     0     0``

``errors: No known data errors``

Mirror (RAID 1) Expand to more disks
------------------------------------
Creating a mirror with more than 2 disks is possibe in that you create an additional mirror (with one disk).
``# zpool`` **``add``** ``<Pool name> mirror <Device 3>``

Repeat the step for more disks.
**zpool status** will show a mirror [VDEV](../../../../../../Glossary/ZFS/VDEV.md) per additional disk.
### Examlpe
``# zpool add mypool mirror sdc``
In this case zool status will show two mirror [VDEVs.](../../../../../../Glossary/ZFS/VDEV.md)
  ``pool: mypool``
 ``state: ONLINE``
  ``scan: none requested``
``config:``

``NAME        STATE     READ WRITE CKSUM``
``mypool      ONLINE      0     0     0``
  ``mirror-0  ONLINE      0     0     0``
``/dev/sda  ONLINE     0     0     0``
``/dev/sdb  ONLINE     0     0     0``
  ``mirror-1  ONLINE      0     0     0``
``/dev/sdc  ONLINE     0     0     0``

``errors: No known data errors``

RAIDZ[1] (RAID 5)
-----------------
Create a pool with a [VDEV](../../../../../../Glossary/ZFS/VDEV.md) group with 1 parity disk striped over at least 3 disks.
``# zpool create <Pool name> raidz <Device 1> <Device 2> <Device 3>``
### Examlpe
``# zpool create mypool raidz sdb sdc sdd``

RAIDZ2 (RAID 6)
---------------
Create a pool with a [VDEV](../../../../../../Glossary/ZFS/VDEV.md) group with 2 parity disk striped over at least 4 disks.
``# zpool create <Pool name> raidz2 <Device 1> <Device 2> <Device 3>`` ``<Device 4>``

RAIDZ3
------
Create a pool with a [VDEV](../../../../../../Glossary/ZFS/VDEV.md) group with 3 parity disk striped over at least 5 disks.
``# zpool create <Pool name> raidz3 <Device 1> <Device 2> <Device 3> <Device 4> <Device 5>``

RAID 10
-------
Creating something like a RAID 10 is possible with adding two mirrored [VDEV](../../../../../../Glossary/ZFS/VDEV.md)s together.
``# zpool create <Pool name> mirror <Device 1> <Device 2> mirror <Device 3> <Device 4>``
### Examlpe
``# zpool create mypool mirror sdb sdc mirror sdd sde``

Additional configuration
------------------------
### Pool root dataset mountpoint
Set the pool mountpoint while creating the pool. Without it will be /<Pool name> (on Ubuntu).
``# zpool create <Pool name> -m <Mount path>`` ``mirror <Device 1> <Device 2> ...``
Mount path	Must be an absolute path, "legacy", or "none".
legacy: not automounted. Mounted by fstab or mount command.
none:	Never mounted -> unmountable -> Still writeable be accessing the dataset

ZFS is mounted automatically without a fstab entry.
#### Examlpe
``# zpool create mypool -m /mnt/mypool mirror sdb sdc``
### Pool mountpoint
Create a pool with one disk mounted to /<Pool mountpoint>.
``# zpool create -R /<Pool mountpoint> <Pool name> <Device>``
#### Examlpe
Create a pool with one disk and a root dataset **mypool2** mounted to **/myroot/mypool2**.
``# zpool create -R`` /myroot ``create mypool2 sdb``

