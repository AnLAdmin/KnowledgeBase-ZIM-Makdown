# Windows
Created Samstag 23 November 2024

Install the client as user or admin with 

Install
-------
### manual
Download the Windows executable **bin.windows.incus.x86_64.exe** from the [Github release page](https://github.com/lxc/incus/releases).
Rename it to incus.exe and move it to a appropriate location.
Extend path with that location.

### by Winget
As user
``PS> winget install LinuxContainers.Incus``

Machine-wide install does not work. Seems to be an MSIX package.

### by Chocolatey
``PS>  choco install incus``

Configure [Remote access over TLS](../../../Configuration/Remote_access.md).

Configure
---------
Configure [Remote access over TLS](../../../Configuration/Remote_access.md).

