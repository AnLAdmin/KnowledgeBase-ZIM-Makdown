# Examples
Created Mittwoch 06 Januar 2021

Create log entries with leading date/time
-----------------------------------------
```sh
echo "$(date +"%d.%m.%y %H:%M:%S") - SNAP_NAME: $SNAP_NAME" >>/var/log/btrfs_create_filesystem_snapshot.out
echo "$(date +"%d.%m.%y %H:%M:%S") - SNAP_MOUNTPOINT: $SNAP_MOUNTPOINT" >>/var/log/btrfs_create_filesystem_snapshot.out
```

