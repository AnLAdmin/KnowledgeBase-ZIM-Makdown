# Resize
Created Montag 20 Januar 2020

-> You can grow a logical volume online. You'd have to unmount it to shrink it

In partition
------------
First [resize partition](../../Partition/Resize.md).
Than resize ext fs by all free space in the partition:
# resize2fs /dev/<Partition>
Resize 
# resize2fs /dev/<Partition> <Size><Unit>

In LVM
------
First [resize partition](../../Partition/Resize.md). Than [resize LVM PV](../../LVM/Physical_volume/Resize.md). After that [resize LVM LV](../../LVM/Logical_Volume/Resize.md).
At the end resize ext fs by all free space in the LV:
# resize2fs  /dev/mapper/vg-root
Resize to a specific size (base two)
# resize2fs  /dev/mapper/vg-root <Size><Unit>

Unit:
s	sectors (512 bytes)
K	KiB
M	MiB
G	GiB


