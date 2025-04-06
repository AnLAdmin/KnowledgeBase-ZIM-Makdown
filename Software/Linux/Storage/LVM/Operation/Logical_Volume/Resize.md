# Resize
Created Montag 20 Januar 2020

-> You can grow a logical volume online. You'd have to unmount it to shrink it

Resize a LVM logical volume:
All free space in the volume group:
# lvextend <VG>/<LV>
By a specific size (base  two):
# lvextend <VG>/<LV> -L+<Size><Unit>
By physical extends:
# lvextend <VG>/<LV> -l+<Number>

unit:
b|B		bytes
k|K		KiB
m|M	MiB
g|G		GiB
t|T		TeB
p|P		PeB
e|E		ExB
s|S		sectors
	

