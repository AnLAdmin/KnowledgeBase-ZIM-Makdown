# Replace failed disk with new
Created Freitag 11 Oktober 2024

>= Windows Server 2012 R2

The Server manager does not have all tools to replace a failed disk in a pool. Use Powershell.

Remove physicaly the failed physical disk.
You can also remove it at the end. It depends how the disk failed. If your system hangs because of a failed disk, it's probably necessary to remove it before this workflow.
[List pools](./List_pools.md) to check which is degraded.
[List the physical disks](./List_physical_disks_of_a_pools.md) of the degraded pool.
FriendlyName    CanPool   OperationalStatus   HealthStatus   Usage         Size
------------    -------   -----------------   ------------   -----         ----
PhysicalDisk3   False     OK                  Healthy        Auto-Select   5.46 TB
PhysicalDisk-1  False     Lost Communication  Warning        Retired       5.46 TB
Check **OperationalStatus** or **HealthStatus** to find the (removed) failed disk. Remember the **FriendlyName**.
Retire the failed disk:
``PS> Set-PhysicalDisk -FriendlyName <Disk friendly name> -Usage Retired``

**Before you add the new disk remember the serial number or other specific attributes (model, size, ...) to the new disk.**
List disks to get the FriendlyName of the new disk:
PS> Get-PhysicalDisk | select FriendlyName,Model,Size,SerialNumber | ft -AutoSize
Add the new disk to the pool:
PS> Add-PhysicalDisk -PhysicalDisks <Disk friendly name> -StoragePoolFriendlyName <Storage pool friendly name>

[List virtual disks](./List_Virtual_disk_of_a_pool.md) of the degraded pool.
Repair degraded (Marked with warning in HealthStatus) virtual disk:
``PS> Repair-VirtualDisk –FriendlyName "<Virtual disk friendly name>"``

Check repair status:
``PS> Get-StorageJob``

After the repair finished remove the failed disk from the pool:
``PS> Remove-PhysicalDisk –PhysicalDisks (Get-PhysicalDisk | Where-Object {$_.Usage -eq 'Retired'}) –StoragePoolFriendlyName <Pool friendly name>``

