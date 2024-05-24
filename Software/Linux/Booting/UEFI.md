# UEFI
Created Freitag 01 November 2019

Usage hints
-----------

### Check BIOS mode

#### Linux
On kernel >4. If the file does not exist, then the system was not bootet in UEFI mode.
$ cat ``/sys/firmware/efi/fw_platform_size``

#### macOS
<2008 Macs: IA32 EFI 1.x
>=2008 Macs: x86_64 EFI 1.x
Apple's EFI implementation is not fully compliant witn the
$ ioreg -l -p IODeviceTree | grep firmware-abi

#### Windows
Start **msinfo32.exe**.
Values of "System Type" and "BIOS mode":
64bit Win + UEFI 64: System Type: x64-based PC, BIOS mode: UEFI
32bit Win + UEFI 32: System Type: x86-based PC, BIOS mode: UEFI
-> Win 64 does not support booting on a UEFI 32.

### EFI Boot methods

#### EFISTUB
Kernel compiled with [EFISTUB](https://wiki.archlinux.org/index.php/EFISTUB) to run directly from EFI [ESP]() placed in 
Find location of [ESP]() (Ubuntu: /boot/efi) :
# findmnt efi
Store linux initrd and kernel relativly to [ESP:]()
<esp>/EFI/ubuntu/initrd.img-xxx
<esp>/EFI/ubuntu/vmlinux-xxx
Create boot entry:
# efibootmgr --disk /dev/sdX --part Y --create --label "Arch Linux" --loader /vmlinuz-linux --unicode 'root=<PARTUUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX> rw initrd=<\initrd.img-xxx>' --verbose
X: disk number
Y: partition number
Set boot order:
# efibootmgr --bootorder XXXX,XXXX --verbose
XXXX: Number of boot entry

#### Boot manager
Classical boot manager which has to support EFI:
Grub, [REFInd,](https://www.rodsbooks.com/refind/) ...

### Add a boot option

1. The disk containing the EFI system partition (ESP). E.g.: /dev/sda, /dev/nvme0n1.
2. The partition number of the ESP on that disk. The Y in /dev/sdaY or /dev/nvme0n1pY.
3. The path to the EFI application (relative to the root of the ESP)

# efibootmgr --create --disk /dev/sda --part 1 --loader /EFI/refind/refind_x64.efi --label "rEFInd Boot Manager" --verbose

Tools
-----

### efibootmgr
[Homepage](https://github.com/rhboot/efibootmgr)
Tool to manipulate UEFI Firmware Boot Manager Settings like boot order, boot devices, ...

