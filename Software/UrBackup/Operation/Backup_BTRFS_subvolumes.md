# Backup BTRFS subvolumes
Created Freitag 08 Januar 2021

UrBackup doesn't backup unmounted BTRFS subvolumes even if they are defined as backup targets.
The following describes what to do to backup unmounted subvolumes.

Client changes
--------------
Insert the following code to **/usr/local/share/urbackup/btrfs_create_filesystem_snapshot** on the *backup client* to *create snapshot* at a relative path similar to the originals location ([Src](https://<Service name FQDN>/master/Config_UrBackup/src/branch/Backup-BTRFS-subvolumes/Client/usr/local/share/urbackup/btrfs_create_filesystem_snapshot)):
```sh
if [[ $TYPE == "btrfs" ]]
then
... # Insert after
        # CUSTOM - This creates only one snapshot to backup one subvolume
        if [[ $SNAP_MOUNTPOINT != $SNAP_ORIG_PATH  ]]; then
            if [ 256 -eq $(stat --format=%i $SNAP_ORIG_PATH) ]; then
                SNAP_DEST="$SNAP_MOUNTPOINT/.urbackup_snaps/$SNAP_ID"
                mkdir -p $SNAP_DEST$(dirname $SNAP_ORIG_PATH)
                btrfs subvolume snapshot -r "$SNAP_ORIG_PATH" "$SNAP_DEST$SNAP_ORIG_PATH"

                echo "SNAPSHOT=$SNAP_DEST"
                exit 0
            fi
        fi
        # CUSTOM - END
... # Insert before

        mkdir -p "$SNAP_MOUNTPOINT/.urbackup_snaps"
...
```

Insert the following code **/usr/local/share/urbackup/btrfs_remove_filesystem_snapshot** on the backup client to remove the special subvolume snapshot after backup ([Src](https://<Service name FQDN>/master/Config_UrBackup/src/branch/Backup-BTRFS-subvolumes/Client/usr/local/share/urbackup/btrfs_remove_filesystem_snapshot)):
```sh
if [[ $TYPE == "btrfs" ]]
then
... # Insert after
        # CUSTOM - This creates only one snapshot to backup one subvolume
        if [[ $SNAP_DEST == *$SNAP_NAME*  ]]; then
            if [ 256 -eq $(stat --format=%i $SNAP_ORIG_PATH) ]; then
                btrfs subvolume delete "$SNAP_DEST"
                rm -Rf "$SNAP_MOUNTPOINT"
                exit 0
            fi
        fi
        # CUSTOM - END
... # Insert before

        btrfs subvolume delete "$SNAP_MOUNTPOINT"

```


Server web interface
--------------------
*Optionally* create a vitual client if you want to also backup a subvolume besides normal directories in mounted volumes.
Specify the path to the subvolume (only one) in the client settings **Default directories to backup**. UrBackup only creates one snapshot per mounted volume.

