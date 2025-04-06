# noCOW
Created Samstag 12 Oktober 2019

Disable
-------

* Mount with option **nodatacow**
* chattr +C [/dir/file](/dir/file)

Note: From chattr man page: "For btrfs, the 'C' flag should be set on new or empty files. If it is set on a file which already has data blocks, it is undefined when the blocks assigned to the file will be fully stable. If the 'C' flag is set on a directory, it will have no effect on the directory, but new files created in that directory will have the No_COW attribute."
Tips on [ArchLinux Wiki](https://wiki.archlinux.org/index.php/Btrfs#Disabling_CoW).

Snapshots and noCOW
-------------------
It cancels copy-on-write for data blocks, unless there is a snapshot.

There is no problem with creating a snapshot of a subvolume mounted with nodatacow. But since cow is required to create a snapshot, when you create one on a subvolume with nodatacow it will essentially ignore nodatacow; acting as it normally would.

That does however bring up an interesting question: Is the nodatacow ignored permanently? Does creating a snapshot of a subvolume with COW disabled, reenable COW until it's manually disabled again?

Luckily, no. From the btrfs mailing list...
On a NOCOW file the first write to a fileblock (4096 bytes) after a snapshot must still be COW, because the snapshot locks the old version in place, and now the fileblock has changed, so it MUST be written elsewhere despite the NOCOW in ordered to keep the snapshot as it was. However, the file does retain the NOCOW attribute and additional writes to the same fileblock will be in-place... until the next snapshot of course.

