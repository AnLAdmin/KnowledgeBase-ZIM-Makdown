# Shutdown VM
Created Sonntag 25 August 2024

([Src](https://www.libvirt.org/manpages/virsh.html#shutdown))

Shutdown by OS
--------------
This shutdowns the VM gracefully with a OS shutdown if possible:
$ virsh shutdown <VM name>

It will pick a suitable method to signalize the shutdown to the os. See [Shutdown by specific mode](#shutdown-by-specific-mode).

Shutdown by specific mode
-------------------------
This specifies the way to signal the os a shutdown:
$ virsh shutdown <VM name> --mode <Mode name>
Mode name:	 acpi, agent, initctl, signal, paravirt

