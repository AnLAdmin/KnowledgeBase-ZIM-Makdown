# Storages spaces
Created Sonntag 15 März 2020

Add disk to pool
----------------
Prepare replacement disk:
Remember model and serial number of the new disk before you connect it to your PC.
[Find](../Storage_Management/Disks/List.md) the unique ID of thenew disk.
[Clear](../Storage_Management/Disks/Clear.md) and [reset](../Storage_Management/Disks/Remove_storage_spaces_metadata.md) the new disk.
Go to **Manage Storage spaces** - **Change settings - ***Add drives*.
Select the replacement drive(s) and click Add drives.

### Errors

#### Can't add drivers (Error code 0x00000032)
You have to [reset](../Storage_Management/Disks/Remove_storage_spaces_metadata.md) the disk. -> diskpart clean / PS>Clear-Disk <number> is not enough.


