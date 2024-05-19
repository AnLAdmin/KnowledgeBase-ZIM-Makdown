# Linux
Created Dienstag 16 November 2021

Variables
---------
URL to APC UPS:		URL to Network Management Card 2 of the APC UPS
Host:			Device were PowerChute is runnig on.
UPS IP:			IP address of thr APC UPS
Outlet group:		Outlet group were the device is connected. Look into device configuration or at the back of the UPS.
-> Viewed from behind **left** is ***Main outlet*** and **right** is *Group* 1.
UPS shutdown delay:	Delays before the UPS shutdown starts (UPS shutdown = Includes OS and/or specified services shutdowns).

Setup
-----
Login to <Host> with SSH.
Download [software](https://www.apc.com/shop/us/en/categories/power/uninterruptible-power-supply-ups-/ups-management/powerchute-network-shutdown/N-auzzn7) with wget.
Unpack tar.gz:
# tar -xf pcns<Version>.tar.gz
cd into **Linux_x64**.
This installs the PowerChute service:
# ./install.sh
>Choose language
> 1
> Do you agree to the above license terms? [yes or no]
> yes
> ... install to the default directory (/opt/APC/PowerChute): 
> [ENTER]
> Are you sure you want to install PCNS to /opt/APC/PowerChute [Yes|No]?
> yes

### Firewall
Create an PowerChute application for UFW **/etc/ufw/applications.d/PowerChute**:
```ini
[PowerChute]
title=APC PowerChute Network shutdown service
description=APC PowerChute Network shutdown management web interface
ports=6547/tcp|3052/udp
```

# ufw allow PowerChute

Open the browser at [https://<Host>:6547/cfgwizard](https://<Host>:6547/cfgwizard)
Disable **Join PowerChute Customer Experience Improvement Program ("CEIP")**.
Choose **IPv4**.
**No **SCVMM support.
UPS configuration: **Single**.
PowerChute Setup: Security
User Name:		device
Password:		<Keepass **NMC SuperUser (APC UPS)**>
Authentication Phrase:	<Keepass **Shutdown Authentication Phrase**>
PowerChute Setup: UPS Details
Protocol:				https
Accept Untrusted SSL Certificates:	enabled
Port:					443
IP Address:				<UPS IP>
Start Registration.
Select <Outlet group>.
OPTIONALLY PowerChute Setup: Virtualization Settings
VM Shutdown:		enabled
VM Shutdown Duration:	<VM Shutdown Duration>
**The shutdown of the OS and services has to be *in* the *time* *frame* defined by *__Low Battery Duration__* on the UPS. **
**(NMC web interface *Configuration - Shutdown*).**
VM Startup:		enabled
Startup Duration:	<VM Shutdown Duration>
PowerChute Setup: UPS Shutdown
Enable **Turn off the UPS**.
After the installation browse in the [web interface](https://<Host>:6547/) to <Host> - Configure Events and set the following for the Event UPS on Battery:
Logging:		enabled
Shutdown:
Enable Shutdown:	enabled
Delay:			<UPS shutdown delay>

