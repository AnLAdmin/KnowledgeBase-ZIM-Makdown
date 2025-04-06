# Import iso as volume
Created Freitag 06 Dezember 2024

([Src](https://linuxcontainers.org/incus/docs/main/reference/devices_disk/#types-of-disk-devices))

This creates a volume to later attach as a ROM device to a vm.
$ ``incus storage volume import <Storage pool> <Path to image.iso> <Volume name> --type=iso``
### Example
$ ``incus storage volume import my_pool /home/myuser/win11x64.incus.iso my_iso-volume --type=iso``

