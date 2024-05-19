# Replace a disk in a pool
Created Donnerstag 18 August 2022

Direct
------
Show current situation. List disks:
# lsblk --output NAME,LABEL,MOUNTPOINT,SIZE,TYPE,FSTYPE,UUID 
(alias lshd on my system)
List pools:
# btrfs filesystem show

Replace a disk. Mount top level volume of the pool. Start online replacing:
@ btrfs replace start [-f] <Old device|Devid> <New device> <(Toplevel) mountpoint>
-f: Force overwrite of the target / new disk.
Check status until finished:
# btrfs replace status <(Toplevel) mountpoint>

Check if a balance is necessary with:
# btrfs filesystem df <Mountpoint> 
Data, RAID1: total=1.78TiB, used=1.57TiB
Data, single: total=1.34TiB, used=5.25MiB
System, RAID1: total=8.00MiB, used=320.00KiB
System, single: total=64.00MiB, used=160.00KiB
Metadata, RAID1: total=150.00GiB, used=121.06GiB
Metadata, single: total=104.00GiB, used=0.00B
GlobalReserve, single: total=512.00MiB, used=0.00B
If there are still single and RAID mixed, like in the following output, start a balance:
# btrfs balance start -dconvert=raid1 -mconvert=raid1 <Mountpoint>

Umnount top level volume after replace or balance is finished.

Through add and remove
----------------------
[Add](./Add_disk_to_an_existing_filesystem.md) a new disk.
Remove the missing/problematic one.

