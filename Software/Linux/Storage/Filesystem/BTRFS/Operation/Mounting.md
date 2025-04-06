# Mounting
Created Dienstag 11 Februar 2020

One can mount a whole BTRFS disk or partition like other filesystems. One can also mount Subvolume/snapshots. See [mount options](./Mounting/Mount_options.md).
fstab

by command mount
----------------
``# mount -L <Disk label> -o subvol=<Subvol name>,compress=lzo``

