# Hot unplug
Created Donnerstag 18 August 2022


1. Unmount any filesystems on the disk. (umount ...)
2. Deactivate any LVM groups. (vgchange -an)
3. Make sure nothing is using the disk for anything.
	1. You Could unplug the HDD here, but it is recommended to also do the last two steps
4. OPTIONAL: Spin the HDD down. (irrelevant for SSD's) (sudo hdparm -Y /dev/(whatever))
5. Tell the system, that we are unplugging the HDD, so it can prepare itself. (echo 1 | sudo tee /sys/block/(whatever)/device/delete)


If you want to be extra cautious, do echo 1 | sudo tee /sys/block/(whatever)/device/delete first. That'll unregister the device from the kernel, so you know nothing's using it when you unplug it. When I do that with a drive in an eSATA enclosure, I can hear the drive's heads park themselves, so the kernel apparently tells the drive to prepare for power-down.

If you're using an AHCI controller, it should cope with devices being unplugged. If you're using some other sort of SATA controller, the driver might be confused by hotplugging.

In my experience, SATA hotplugging (with AHCI) works pretty well in Linux. I've unplugged an optical drive, plugged in a hard drive, scanned it for errors, made a filesystem and copied data to it, unmounted and unplugged it, plugged in a differerent DVD drive, and burned a disc, all with the machine up and running.

