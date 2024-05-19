# Checks
Created Freitag 08 Februar 2019

@BSD @Linux


Smartctl tests
Short test:
smartctl -t short /dev/adaX

Conveyance test:
smartctl -t conveyance /dev/adaX

Long test:
smartctl -t long /dev/adaX

Badblocks test:
Enable the kernel geometry debug flags
sysctl kern.geom.debugflags=0x10

Run badblocks on each drive (4096 block due to 6TB size):
badblocks -b 4096 -ws /dev/adaX


