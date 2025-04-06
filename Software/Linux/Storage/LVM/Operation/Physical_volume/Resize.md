# Resize
Created Montag 20 Januar 2020

-> You can grow a logical volume online. You'd have to unmount it to shrink it

After the partition was [resized](../../../Partition/Resize.md) resize the LVM PV.
Resize to all free space in partition:
# pvresize /dev/<Partition> 
Resize to a specific size:
# pvresize --setphysicalvolumesize <Size><Unit> /dev/<Partition>

unit:
b|B		bytes
k|K		KiB
m|M	MiB
g|G		GiB
t|T		TeB
p|P		PeB
e|E		ExB
s|S		sectors

