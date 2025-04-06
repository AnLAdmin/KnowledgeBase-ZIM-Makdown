# Create fstab entry per btrfs toplevel volume
Created Samstag 15 Juni 2024

Add <Toplevel admin point> to /etc/fstab:
```sh
LABEL=<disk/partition label>    <Toplevel admin point>    btrfs   <mount options>   0   1
```
E.g.
```sh
LABEL=Root   /root/mnt/btrfs/root   btrfs   noauto,noatime,nodiratime,space_cache=v2,compress=lzo   0   0
LABEL=Root   /root/mnt/btrfs/md2    btrfs   noauto,subvol=/                                         0   1
LABEL=Data   /srv/vm                btrfs   noatime,subvol=@virtualization,compress=lzo             0   0
```

