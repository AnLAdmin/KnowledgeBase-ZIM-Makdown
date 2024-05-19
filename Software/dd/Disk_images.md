# Disk images
Created Dienstag 11 Februar 2020

Uncompressed
------------
 # dd if=/dev/sda of=/tmp/sdadisk.img

Compressed
----------
# dd if=/dev/vda | gzip -c >/tmp/vdadisk.img.gz

Restore uncompressed image
--------------------------
# dd if=/tmp/sdadisk.img of=/dev/sda

Restore compressed image
------------------------
# gzip -dc /tmp/vdadisk.img.gz | dd of=/dev/vda

