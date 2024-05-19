# 0 Issues
Created Sonntag 28 April 2024


* ☐ Issue: systemd-networkd-wait-online.service needs long (>1min) during startup


### Problem
During bootup the service systemd-networkd-wait-online.service waits for all interfaces to be up. If the computer has unconnected NIC the service will need long to proceed.
### Solution
([Src](https://unix.stackexchange.com/questions/710089/systemd-networkd-wait-online-service-consistently-overwritten-by-updates))
Besides connecting the other devices is to exclude them from probing in the services unit file.
Edit systemd-networkd-wait-online.service file:
# systemctl edit systemd-networkd-wait-online.service
To exclude interfaces only add the ones you want to wait for with **-i <Interface name>:degraded**:
```sh
[Service]
ExecStart=
ExecStart=/usr/lib/systemd/systemd-networkd-wait-online -i enp12s0:degraded
```
or tell the service to react to any NIC who is first connected by set the parameter **--any**:
```sh
[Service]
ExecStart=
ExecStart=/usr/lib/systemd/systemd-networkd-wait-online --any
```
#### Explanation
This workflow doesn't overwrite the original unit file. It adds an overwrite file at **/etc/systemd/system/systemd-networkd-wait-online.service.d/override.conf**.

