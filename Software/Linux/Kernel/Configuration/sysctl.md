# sysctl
Created Samstag 18 Juli 2020

Controls the kernel variables.

Set variable temporary
----------------------
# sysctl variable=value

Set variable permanently
------------------------
Edit **configuration**. -> [Reload](./sysctl/Reload.md) variables without reboot.

### Configuration file locations

1. /run/sysctl.d/*.conf
2. /etc/sysctl.d/*.conf
3. /usr/local/lib/sysctl.d/*.conf
4. /usr/lib/sysctl.d/*.conf
5. /lib/sysctl.d/*.conf
6. /etc/sysctl.conf


