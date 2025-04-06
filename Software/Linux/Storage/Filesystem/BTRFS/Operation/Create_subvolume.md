# Create subvolume
Created Samstag 15 Juni 2024


Mount toplevel volume:
``# mount /root/mnt/btrfs/<dev>``
Create subvolume with name @<name> in mountpoint \root\mnt\btrfs\<dev>:
``# btrfs subvolume create <mountpount>[/<dir>]/<subvolume name>``

Set access rights:
Change owner:
``# chown <owner>:<group> <Toplevel admin point>/<subvolume>``
Change access attributes:
``# chmod <access attrs> <Toplevel admin point>/<subvolume>``
Unmount top level volume if finished:
``# umount <Toplevel admin point>``


