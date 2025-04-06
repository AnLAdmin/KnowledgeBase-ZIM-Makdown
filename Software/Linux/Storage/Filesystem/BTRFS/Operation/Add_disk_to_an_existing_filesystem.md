# Add disk to an existing filesystem
Created Donnerstag 18 August 2022

Adds a disk to a single filesystem or a pool.

Mount toplevel volume (if necessary):
# mount <mountpoint>
Add disk:
# btrfs device add /dev/sd[a-z][1-] <mountpoint> (Add -f if necessary to force overwrite)
Check pool:
# btrfs filesystem show /dev/sd[a-z][1-]
Activate RAID (redistribute data based on RAID level):
If there already are more than 1 disk:
# btrfs balance start <mountpoint>
If there was only 1 disk:
# btrfs balance start -dconvert=raid1 -mconvert=raid1 <mountpoint>
Check status ob the balance:
# btrfs balance status <mountpoint>
Check balance result:
# btrfs fi df <mountpoint>

