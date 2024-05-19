# List
Created Sonntag 15 März 2020

PS A> Get-PhysicalDisk

With UniqueId
-------------
The UniqueId can beside the Friendly name be usesd to select a disk to manipulate.
PS A> Get-PhysicalDisk | ft FriendlyName, SerialNumber, UniqueId -auto

