# File locations
Created Samstag 02 Januar 2021

Linux
-----

### Urbackup configuration and scripts
/etc/default

### Executable
/usr/local/bin

### Default configuration and scripts
/usr/local/etc/urbackup 

Backup DB or snapshot a filesystem

### Application scripts
/usr/local/share/urbackup	 

E.g. pre/post scripts and urbackup client public key (for auth with urbackup server).

### Data files
/usr/local/var/urbackup


* Directories/files to backup.
* Client configuration on the server


### Systemd unit file
/lib/systemd/system

Do not delete without disabling the service with systemctl first.

