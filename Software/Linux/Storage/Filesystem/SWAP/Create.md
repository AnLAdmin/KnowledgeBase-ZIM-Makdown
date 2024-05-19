# Create
Created Donnerstag 27 Februar 2020

On partition
------------
# mkswap -L <Label name> <partition> 
# swapon <partition>

### Example
# mkswap -L SWAP1 /dev/sda2 
# swapon /dev/sda2
or edit fstab first and than
# swapon -a

On filesystem
-------------
# fallocate -l <size in byte> <swapfile>
Size:	File size in Kib, MiB, GiB, TiB. ... (1024) or M(B),G(B),T(B) (1000)
# mkswap <swapfile> 
# swapon <swapfile>

### Example
# fallocate -l 4G /swapfile1
# mkswap /swapfile1
# swapon /swapfile1

On BTRFS filessystem
--------------------
([Info,](https://btrfs.readthedocs.io/en/latest/Swapfile.html) See also restrictions and examples)
Create a subvolume to store swap files in (because a BTRFS volumes with swap files can't be snapshoted):
# btrfs sub create /swapfiles
Change subvolume access rights only to root:
# chmod 700 /swapfiles
### Create swap file
#### BTRFS version >6.1
# btrfs filesystem mkswapfile --size <Swap file size> /swapfiles/<Swap file name>
#### BTRFS version <6.1 (Ubuntu <=22.04)
# truncate -s 0 /swapfiles/<Swap file name>
# chattr +C /swapfiles/<Swap file name>
# fallocate -l <Swap file size> /swapfiles/<Swap file name>
# chmod 0600 /swapfiles/<Swap file name>
# mkswap /swapfiles/<Swap file name>
#### Activate swap file
# swapon /swapfiles/<Swap file name>

Edit /etc/fstab to make it permanent
------------------------------------
```ini
<swapfile | partition>   none    swap    sw[,pri=<Swap priority (use minus)>    0   0
```
### Example
```ini
 /dev/disk/by-uuid/40206ea3-f325-47a8-bfa7-246a15323086  none    swap    sw,pri=-2    0   0
```

Define swapiness
----------------
# sysctl vm.[swappiness](https://wiki.archlinux.org/title/Swap#Swappiness)=<x>
x:	0...100 -> smaller is less swapiness -> less swaping (for anonymouse memory pages), 0 is more file backed memory swapping
  Default = 60
Additional infos on [howtogeek](https://www.howtogeek.com/449691/what-is-swapiness-on-linux-and-how-to-change-it/).

Make *swapiness* change permanent
---------------------------------
Add to file /etc/sysctl.d/60-MY-settings.conf:
```sh
vm.swappiness=<x>
```

Alternative SWAP options for performance
----------------------------------------
<EXTEND see hints [here](https://wiki.archlinux.org/title/Swap)>

