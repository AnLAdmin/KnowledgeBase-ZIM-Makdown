# Create filesystem
Created Sonntag 28 April 2024

Format a FAT32 partition:
# mkfs.fat -F <FAT size> -n <Label name> /dev/<Partition name>
FAT size:	FAT type 12, 16 or 32 (Newest and prefered 32)
Label name:	Name of the filesystem (partition name)
Label length 
short name:	<=11, 8.3
long name:	<=255
### Example
Format a FAT32 partition with name DOS:
# mkfs.fat -F 32 -n DOS /dev/sda1

