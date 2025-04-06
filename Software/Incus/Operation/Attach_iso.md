# Attach iso
Created Samstag 07 Dezember 2024

([Src](https://linuxcontainers.org/incus/docs/main/reference/devices_disk/#types-of-disk-devices))

By volume
---------
This uses a beforehand into a volume type ISO [imported](./Import_iso_as_volume.md) ISO file.
Add the volume of type ISO.
$ ``incus config device add <Instance name> <Device name> disk pool=<Storage pool name> source=<ISO volume name> boot.priority=10``
### Example
``$ incus config device add vmWin11 iso-volume disk pool=<pool> source=iso-volume boot.priority=10``

By source path
--------------
Connect a ISO file directly to the instance.
``$ incus config device add <Instance name> <Device name> source=<Path to ISO file> boot.priority=10``
### Example
``$ incus config device add vmWin11 Win11_setup_disk disk source=/home/myuser/Win11_23H2_English_x64.incus.iso boot.priority=10``

