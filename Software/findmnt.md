# findmnt
Created Samschtig 09 Novämber 2019
@Linux

findmnt will list all mounted filesystems or search for a filesystem. (Source: man) 
Can also find the top

Other usages
------------

### Find mount point of current directory
$ findmnt -T . 

### Get UUID of filesystem / BTRFS toplevel volume
$ findmnt -o UUID -T <Dir/mountpoint/subvolume>

