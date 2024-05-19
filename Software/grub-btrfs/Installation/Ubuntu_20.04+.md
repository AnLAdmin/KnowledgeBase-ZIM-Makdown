# Ubuntu 20.04+
Created Sonntag 19 Mai 2024

Make file
---------
### Dependencies

* btrfs-progs
* grub
* bash >4
* gawk
* inotify-tools (Only when using the grub-btrfsd daemon to update grub menu)
* make

# apt install inotify-tools make

Download [grub-btrfs](https://github.com/Antynea/grub-btrfs) into ~:
# wget <https://github.com/Antynea/grub-btrfs/archive/master.zip>
# unzip master.zip

Start installation:
# cd grub-btrfs-master/
# make install
-> *make help* shows  install options

Enable and start systemd **grub-btrfsd.service**:
# systemctl enable grub-btrfsd.service
# systemctl start grub-btrfsd.service

Cleanup:
$ cd ~
$ rm master.zip
$ rm grub-btrfs-master

Manual
------
Download [grub-btrfs](https://github.com/Antynea/grub-btrfs) into ~:
# wget <https://github.com/Antynea/grub-btrfs/archive/master.zip>
# unzip master.zip

Copy man pages:
# cd grub-btrfs-master
# mv manpages/grub-btrfs.8.man manpages/grub-btrfs.8
# mv manpages/grub-btrfsd.8.man manpages/grub-btrfsd.8
# bzip2 manpages/grub-btrfs.8
# bzip2 manpages/grub-btrfsd.8
# cp manpages/grub-btrfs.8.bz2 /usr/share/man/man8/
# cp manpages/grub-btrfsd.8.bz2 /usr/share/man/man8/

Copy **update-grub** script:
# cp 41_snapshots-btrfs /etc/grub.d/
# chmod 755 /etc/grub.d/41_snapshots-btrfs
# mkdir /etc/default/grub-btrfs/

Copy config to /etc/default/grub-btrfs/:
# cp config /etc/default/grub-btrfs/

Edit /etc/default/grub-btrfs/config and enable as follows:
```sh
GRUB_BTRFS_LIMIT="20"
```

# apt install inotify-tools
Copy systemd service files.
Copy daemon file:
# cp grub-btrfsd /usr/bin
Install dependencies:
# cp grub-btrfsd.service /lib/systemd/system/
Enable and start systemd **grub-btrfsd.service**:
# systemctl enable grub-btrfsd.service
# systemctl start grub-btrfsd.service

Update grub:
# update-grub

Cleanup:
$ cd ~
$ rm master.zip
$ rm grub-btrfs-master
