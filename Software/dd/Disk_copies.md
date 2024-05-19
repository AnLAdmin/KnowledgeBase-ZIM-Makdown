# Disk copies
Created Dienstag 11 Februar 2020

This creates a 1:1 copy from the input (if) disk:
# dd if=/dev/sda of=/dev/sdb bs=4096 conv=noerror,sync

bs	Buffer size in bytes. While copying a disk use a multiple of 512 (smallest sector size of a disk). Bigger is better.
noerror	Ignore errors
sync	Synchronized I/O

