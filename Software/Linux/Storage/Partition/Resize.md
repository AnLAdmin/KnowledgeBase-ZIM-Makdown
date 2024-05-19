# Resize
Created Montag 20 Januar 2020

-> You can grow a logical volume online. You'd have to unmount it to shrink it

List partitions.
# parted /dev/<Dev> print list
Resize.
# parted /dev/<dev> resizepart <Part. number> <End>

End:
absolut bytes e.g. 500MiB -> Resize until 500MiB byte.
or -500MiB -> Resize until 500MiB before end of disk.
or 100% all of the available free space.
	
-> Contained filesystems have to be resized with special tools. See Resize in [Filesystem](../Filesystem.md).


