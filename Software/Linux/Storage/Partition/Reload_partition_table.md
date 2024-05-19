# Reload partition table
Created Donnerstag 18 August 2022

Reload partition table after a disk hotplug or parition change:

All partition tables
--------------------
# partprobe [/dev/sd<X>]

Disk specific partition table
-----------------------------
# partprobe /dev/sd<X>

