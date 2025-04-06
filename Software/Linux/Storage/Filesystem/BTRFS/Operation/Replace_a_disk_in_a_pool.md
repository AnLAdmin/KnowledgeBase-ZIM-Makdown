# bmoReplace a disk in a pool
Created Donnerstag 18 August 2022

This can be used for a normal working disk or for a failed one. 
-> This does not describe the whole process to handle a failed disk replacement. See here.
Direct
------
Show current situation. List disks:
# lsblk --output NAME,LABEL,MOUNTPOINT,SIZE,TYPE,FSTYPE,UUID 
(alias lshd on my system)
List pools:
# btrfs filesystem show

Find missing BTRFS device ID:
# btrfs device usage <(Toplevel) mountpoint>
-> prefixed with **missing**
E.g:
/dev/sdb, ID: 1
Device size:	5.46TiB
Device slack:	0.00B
Data,RAID1:	1.78TiB
Metadata,single:1.00GiB
Metadata,RAID1:	132.00GiB
System,single:	32.00MiB
System,RAID1:	8.00MiB
Unallocated:	3.55TiB
missing, **ID: 2**
Device size:	0.00B
Device slack:	0.00B
Data,RAID1:	1.78TiB
Metadata,RAID1:	132.00GiB
System,RAID1:	8.00MiB
Unallocated:	3.55TiB

Replace a disk. Mount top level volume of the pool. Start online replacing:
# btrfs replace start [-f] <Old device|Devid> <New device> <(Toplevel) mountpoint>
-f: Force overwrite of the target / new disk.
E.
Check status until finished:
# btrfs replace status <(Toplevel) mountpoint>

Check if a balance is necessary with:
# btrfs filesystem df <Mountpoint> 
Data, RAID1: total=1.78TiB, used=1.57TiB
Data, **single**: total=1.34TiB, used=5.25MiB
System, RAID1: total=8.00MiB, used=320.00KiB
System, **single**: total=64.00MiB, used=160.00KiB
Metadata, RAID1: total=150.00GiB, used=121.06GiB
Metadata, **single**: total=104.00GiB, used=0.00B
GlobalReserve, single: total=512.00MiB, used=0.00B
If there are still single and RAID mixed, like in the output above, start a balance:
# btrfs balance start -dconvert=raid1 -mconvert=raid1 <Mountpoint>

Umnount top level volume after replace or balance is finished.

Through add and remove
----------------------
[Add](./Add_disk_to_an_existing_filesystem.md) a new disk. 
Remove the missing/problematic one.

