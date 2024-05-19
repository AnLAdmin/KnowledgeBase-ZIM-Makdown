# Copy partition table to other disk
Created Sonntag 28 April 2024

**Check the correct disk names** before this commands ;-).
Export table from **source device name**:
# sfdisk -d /dev/<Source device name> > part_table
Create patition table based on the installed root disk:
# sfdisk /dev/<Target device name> < part_table
Check partition creation:
# fdisk -l /dev/<Disk name>

