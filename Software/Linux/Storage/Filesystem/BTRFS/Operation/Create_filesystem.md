# Create filesystem
Created Samstag 15 Juni 2024

Single disk
-----------
Create filesystem:
``# mkfs.btrfs -L <fs label> /dev/sd[a-z][1-] (Add -f if necessary to force overwrite)``
Check volume:
``# btrfs filesystem show /dev/sd[a-z][1-]``

2 disks - Raid 1
----------------
Create filesystem as RAID mirror for metdata and data:
``# mkfs.btrfs -d raid1 -L <fs label> /dev/sd[a-z][1-] /dev/sd[a-z][1-] (Add -f if necessary to force overwrite)``
Check RAID:
``# btrfs filesystem show /dev/sd[a-z][1-]``

2 disks - Raid 0
----------------
Create filesystem as RAID 0 for and data (metadata still RAID 1):
``# mkfs.btrfs -d raid0 -L <fs label> /dev/sd[a-z][1-] /dev/sd[a-z][1-] ... (Add -f if necessary to force overwrite)``
Check RAID:
``# btrfs filesystem show /dev/sd[a-z][1-]``


