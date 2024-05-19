# Installation
Created Mittwoch 08 Januar 2020

Install Windows feature WSL as Administrator:
PS> Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
Reboot.
Download Ubuntu 18.04 LTS:
PS> Invoke-WebRequest -Uri <https://aka.ms/wsl-ubuntu-1804> -OutFile <Download path\>Ubuntu-18.04.appx -UseBasicParsing
or with curl:
PS> curl.exe -L -o <Download path\>ubuntu-1604.appx <https://aka.ms/wsl-ubuntu-18.04>

As normal user
--------------
Install Ubuntu:
PS> Add-AppxPackage <Download path\>app_name.appx
The package will be installed in *C:\Program Files\WindowsApps*.
Ubuntu.exe starts Ubuntu.

On a server
-----------
Extract the <distro>.appx package's contents, e.g. using PowerShell:
PS> Rename-Item ./Ubuntu.appx ./Ubuntu.zip
PS> New-Item -Path 'C:\Program Files\Ubuntu-18.04' -ItemType Directory
PS> Expand-Archive ./Ubuntu.zip "C:\Program Files\Ubuntu-18.04"
Add your distro path to the Windows environment PATH (C:\Users\Administrator\Ubuntu in this example), e.g. using Powershell:
$userenv = [System.Environment]::GetEnvironmentVariable("Path", "machine")
[System.Environment]::SetEnvironmentVariable("PATH", $userenv + ";C:\Program Files\Ubuntu-18.04", "Machine")
Ubuntu.exe starts Ubuntu.

