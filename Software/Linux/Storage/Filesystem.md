# Filesystem
Created Montag 20 Januar 2020

Optimizations
-------------

### TRIM
Usefull for SSD, thin-provisioned storage and virtual images.

#### Periodic TRIM
Preferred.
**Ubuntu** already has a service **fstrim.timer** setup. The timer runs weekly.
The timer relies on the timestamp of **/var/lib/systemd/timers/stamp-fstrim.timer** (which it will create upon first invocation) to know whether a week has elapsed since it last ran. 

#### Continuous TRIM
Alternatively add a filesystem option **discard** in [/etc/fstab.](/etc/fstab.) 
More inforamation can be found [here](https://wiki.archlinux.org/index.php/Solid_state_drive#Periodic_TRIM).

