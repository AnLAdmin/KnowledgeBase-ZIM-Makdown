# Connect to physical console
Created Sonntag 08 Dezember 2024

To access a virtual machines screen like you would with a physical computer, Incus offers a virtual way local or remote by TCP/IP to see the output.
It uses the spice protocol over the Incus API displayed by [Virt-Viewer](../../Virt-viewer.md). The [Incus client](../Installation/Stable/Clients.md) needs a [setup remote](../Configuration/Remote_access.md).

Text console
------------
For devices with text only output.
``$ incus console <VM instance name>``

Graphics console
----------------
For devices with graphic consoles (e.g. Windows, Linux desktops) or to view BIOS/UEFI setup.
``$ incus console <VM instance name> --type=vga``

