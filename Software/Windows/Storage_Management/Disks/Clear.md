# Clear
Created Sonntag 04 Juli 2021

This command clears all partition imformation from disk.

PS A> Clear-Disk -Number <Get **number** with Get-PhysicalDisk and Serial number>

With UniqueId
-------------
PS A> Clear-Disk -UniqueId <Get **UniqueId** with Get-PhysicalDisk and Serial number> [-RemoveOEM]

Force all
---------
PS A> Clear-Disk -UniqueId <UniqueId> -RemoveOEM -RemoveData

-RemoveOEM: Use this to remove an OEM partition. This is a Reserved partition
-RemoveData: Removes all data from disk except a OEM partition.

