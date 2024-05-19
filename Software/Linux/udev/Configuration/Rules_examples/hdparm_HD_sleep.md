# hdparm HD sleep
Created Samstag 04 Juli 2020

Let a harddrive sleep.

Create a file in [rules.d](../../Configuration.md) like **69-hdparm.rules**. The number is the execution priority. The higher the later.
```ini
ACTION=="add", KERNEL=="sd[a-z]", ENV{ID_SERIAL_SHORT}=="WD-WX11D4431992", RUN+="/usr/bin/hdparm -S 241 /dev/%k"
```


ATTENTION
In case of Ubuntu use /*etc/hdparm.conf *instead.

