# Replace a FAILING OR FAILED disk
Created Sonntag 25 August 2024

[Shutdown](../Commands/virsh/Operation/Shutdown_VM.md) the VM gracefully.
-> Evtl. disable mount in fstab and services which use the disk
Remove the HW disk (With shutdown or [hotplug](../../Linux/Storage/Disks/Hot_unplug.md)).
Add the new HW disk (With shutdown or [hotplug](../../Linux/Storage/Disks/Hot_plug.md)).
Find the disk ID to replace later in the VM /dev/disk/by-id/configuration:
# ll /dev/disk/by-id/
[Edit](../Commands/virsh/Operation/Edit_VM_configuration.md) the disk ID (like ata-WDC_WD60EZRX-68L0BN1_WD-WX11D763ZNU8) in the configuration.
[Start](../Commands/virsh/Operation/Start_VM.md) VM.
[Create](./Dump_VM_configuration.md) a backup for the configuration.

OPTIONALLY if it is a replacement of a disk in a BTRFS pool see [here](../../Linux/Storage/Filesystem/BTRFS/Operation/Replace_a_FAILING__or_FAILED_disk_from_a_pool.md).
-> It is possible that the VM will boot in the emergency mode.


