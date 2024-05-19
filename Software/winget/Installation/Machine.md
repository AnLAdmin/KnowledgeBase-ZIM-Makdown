# Machine
Created Samstag 30 Oktober 2021

How to install winget for all users.

Download [Microsoft.VCLibs](https://docs.microsoft.com/en-us/troubleshoot/cpp/c-runtime-packages-desktop-bridge).
Download **Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle** and <xxx>_License1.xml from [Github release page](https://github.com/microsoft/winget-cli/releases).
Install in Powershell as administrator:
PS> Add-AppxProvisionedPackage -online -PackagePath .\Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle -LicensePath .\<xxx>_License1.xml -DependencyPackagePath .\Microsoft.VCLibs.<arch>.<version>.Desktop.appx

