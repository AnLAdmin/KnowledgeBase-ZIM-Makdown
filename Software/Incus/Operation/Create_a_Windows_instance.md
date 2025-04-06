# Create a Windows instance
Created Sonntag 01 Dezember 2024

This creates a windows virtual machine instance.

Create a Windows image
----------------------
Repackage Windows iso with distrobuilder ([Install](../Installation/Stable/Extras.md) if necessary). ([src](https://linuxcontainers.org/distrobuilder/docs/latest/tutorials/use/#repack-windows-iso))
Download Windows iso (You an use [mido.sh](https://github.com/ElliotKillick/Mido/blob/main/Mido.sh)).
$ ./Mido.sh win11x64
Start repackaging (adds drivers):
# ``distrobuilder repack-windows <Original Windows iso> <New Windows iso>``
### Example
# ``distrobuilder repack-windows win11x64.iso win11x64.incus.iso``

Import iso
----------
We [create](./Import_iso_as_volume.md) an volume of the type iso with the volume name **WinXX** (XX = Win version, e.g. Win11). So that we can boot from it later.
### Example
Create an Incus volume of type iso (visible as CD-ROM in guest) with the given iso win11x64.incus.iso  with the name Win11iso.
$ ``incus storage volume import default ./win11x64.incus.iso Win11iso --type=iso``

Create VM
---------
We [create](./Create_VM.md) a VM with a specific CPU count, memory amd boot disk size. 
### Example
This creates a Incus virtual machine instance vmWin11 with 2 CPUs, 6 GiB RAM and a 50 GiB system/boot volume.
``$ incus init vmWin11 --empty --vm -c limits.cpu=2 -c limits.memory=6GiB -d root,size=50GiB``
This creates a Incus virtual machine baced on a profile. The profiles needs to be [created beforehand](#Software:Incus:Operation:Create a Windows instance#create-a-windows-profile).
``$ incus init vmWin11 --empty --vm`` -profile WinSrv2025

Attach the setup iso
--------------------
### as a volume
[Attach](./Attach_iso.md) a setup ISO file to the instance.
#### Example
This attaches the Incus iso volume Win11iso with device name isoWin11 to the VM instance vmWin11.
``$ incus config device add vmWin11 isoWin11 disk pool=default source=Win11iso boot.priority=10``
### as a file

* ☐ Incus: Attach the iso to install as a file @Todo


Add some useful devices
-----------------------
### TPM
[Add](./Add_tpm_to_instances.md) TPM for secure boot and Windows 11 compatibility.
#### Example
``$ incus config device add vmWin11 vtpm tpm [path=/dev/tpm0]``
### SPICE sound
[Add](./Add_raw_instance_configuration_to_instance.md#spice-sound) a spice sound device to the instance through QEMU raw options.
#### Example
``$ incus config set vmWin11 raw.qemu -- "-device intel-hda -device hda-duplex -audio spice"``

OPTIONAL: Attach VirtIO-Win drivers
-----------------------------------
In case distrobuild couldn't (or wouldn't be used you can attach the VirtIO drivers as ISO file.
### Download
Download latest iso from [Fedora](https://fedorapeople.org/groups/virt/virtio-win/direct-downloads/) in the directory **latest-virtio** with a name like **virtio-win-<Version>.iso** with *wget*.
``$ wget https://fedorapeople.org/groups/virt/virtio-win/direct-downloads/latest-virtio/virtio-win.iso``
### Attach to VM instance
[Attach](./Attach_iso.md#by-source-path) the VirtIO ISO directly to the instance.
#### Example
``$ incus config device add vmWin11 Win11_setup_disk disk source=/home/myuser/Win11_23H2_English_x64.incus.iso boot.priority=10``

Start VM the first time
-----------------------
The first time it is important to get to the graphics console fast so that you can press the space bar to enter Windows setup.
### in Virt-viewer on Powershell/CMD
-> Youn need Virt-viewer [installed](../../Virt-viewer/Installation/Windows.md) as a windows applicatication.
Start remote graphics console. This start virt-manager from the console.
``$ incus start <VM instance name> --console=vga``
#### Example
``$ incus start vmWin11 --console=vga``
### in Virt-viewer on WSL
-> Follow [installation](../../Virt-viewer/Installation/WSL_2.md).
Start VM and connect to the graphics console of the VM. This starts virt-manager from the console, connects over the Incus API.
``$ incus start <VM instance name> --console=vga``
### in Virt-viewer on Linux

* ☐ Incus: Start new Windows VM on Linux. @Todo

### on Incus web management

* ☐ Incus: Start new Windows VM on web management. @Todo


Reconnect to VM console during restarts
---------------------------------------
While installling Windows multiple restarts are necessary. While restarting the VM the console connection disconnects (closes Virt-Viewer).
You can [(re)connect](./Connect_to_physical_console.md) to a running VM instance.

Install guest software manual
-----------------------------
### Download
To have the best performance and usability install the VirtIO drivers and the spice guest tools/QEmu agents.
Download latest iso from [Fedora](https://fedorapeople.org/groups/virt/virtio-win/direct-downloads/) in the directory **latest-virtio** with a name like **virtio-win-<Version>.iso**.
### Install
Open iso and execute:

* virtio-win-guest-tools.exe



* ☐ Incus Drivers not loaded see [Forum post](https://discuss.linuxcontainers.org/t/missing-device-driver-on-windows-vm/8204). @Todo


Detach installation medium
--------------------------
[Detach](./Detach_iso.md) install iso from VM. 
### Example
Detach installation media volume iso ``isoWin11 of pool default from instance vmWin11.``
``$ incus storage volume detach default isoWin11 vmWin11 isoWin11``

Windows remote access
---------------------
Configure [RDP](../../UFW/Configuration/Apllication_profiles.md#rdp) port 3389 in firewall (Ubuntu: [UFW](../../UFW/Operation/Add_rule/for_local_access.md) or create an [UFW application profile](../../UFW/Operation/Add_new_app.md) first).

* ☐ Incus: Is it necessary to create a rule to a VM on a default Incus bridge


Misc
----
### Create a Windows profile
I tested this profile with Windows 11/Server 2025. But it will propably also work with older Windows versions.
Create a copy from the **default** profile with name **<Profile name>**.
``$ incus profile copy default`` <Profile name>
Add CPU count to the pofile.
``$ incus profile`` **``set``** ``<Profile name> limits.cpu=<CPU number>``
Add memory size.
``$ incus profile`` **``set``** ``<Profile name> limits.memory=<Memory size><``[``Memory units``](https://linuxcontainers.org/incus/docs/main/reference/instance_units/)``>``
Add audio devices.
``$ incus profile`` **``set``** ``<Profile name> raw.qemu="-device intel-hda -device hda-duplex -audio spice"``
Add system/boot disk.
``$ incus profile device`` **``set``** ``<Profile name> root size=<Storage size><``[``Storage units``](https://linuxcontainers.org/incus/docs/main/reference/instance_units/)``>``
Add virtual TPM.
``$ incus profile device`` **``add``** ``<Profile name> <Device name> tpm [path=<Linux device path]``
Set a description for the profile.
``$ incus profile set <Profile name> --property description="<Profile description>"``
Check your new profil.
``$ incus profile show <Profile name>``
#### Example
Create a profile named **windows11** with 2 CPUs, 4 GiB memory, 30 GiB system disk, audio and a TPM chip. 
-> Windows 11 minimal HW requirements
``$ incus profile set windows11 limits.cpu=2``
``$ incus profile set windows11 limits.memory=6GiB``
``$ incus profile set windows11 raw.qemu="-device intel-hda -device hda-duplex -audio spice"``
``$ incus profile device set windows11 root size=50GiB``
``$ incus profile device add windows11 vtpm tpm path=/dev/tpm0``
``$ incus profile set windows11 --property description="Windows profile: 2 CPU, 4GiB RAM, 30GiB disk, TPM"``
``$ incus profile show windows11``

