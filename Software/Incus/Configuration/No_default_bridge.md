# No default bridge
Created Sonntag 15 September 2024

Setup an incuse **without** the default bridge.

The only change is at the init phase:
``$ incus admin init``
Would you like to use clustering? (yes/no) [default=no]:
Do you want to configure a new storage pool? (yes/no) [default=yes]:
Name of the new storage pool [default=default]:
Name of the storage backend to use (btrfs, dir, lvm) [default=btrfs]:
Would you like to create a new btrfs subvolume under /var/lib/incus? (yes/no) [default=yes]: 
Create a new BTRFS pool? (yes/no) [default=yes]: 
Would you like to create a new local network bridge? (yes/no) [default=yes]: **no**
Would you like to use an existing bridge or host interface? (yes/no) [default=no]:
Would you like the server to be available over the network? (yes/no) [default=no]:
Would you like stale cached images to be updated automatically? (yes/no) [default=yes]:
Would you like a YAML "init" preseed to be printed? (yes/no) [default=no]:

