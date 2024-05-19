# Installation
Created Sonntag 19 Januar 2020

[Source](https://nixos.org/nixos/manual/index.html)

Booting
-------
Set password for nixos.
$ passwd
Start sshd:
$ sudo systemctl start sshd
Connect to ssh server. 
Setting the swiss german keyboard.   

* ☐ nixos setup how to change keyboard @Feature_NixOS


Partitioning and formatting (UEFI)
----------------------------------
3 Partitions: EFI, Swap and Root.
Create a GPT partition table.
# parted /dev/sda -- mklabel gpt

### EFI
Create ESP partition:
# parted /dev/sda -- mkpart [ESP](../../Glossary/EFI/ESP.md) fat32 1MiB 1024MiB
Set flag boot on partition 1 of sda to on.
# parted /dev/sda -- set 1 boot on
Set partition name:
parted /dev/sda -- name 1 ESP
Create filesystem:
# mkfs.fat -F 32 -n ESP /dev/sda1

### Swap
Create swap partition
# parted /dev/sda -- mkpart primary linux-swap 1024MiB 9GiB
Create filesystem:
#mkswap -L SWAP /dev/sda2

### Root
# parted /dev/sda -- mkpart primary 9GiB 100%
Create filesystem (Metadata DUP on HDD is default):
# mkfs.btrfs -L Root /dev/sda3

Installing
----------
Mount filesystem Root:
# mount -t btrfs -o compress=lzo,noatime,nodiratime,space_cache=v2 /dev/sda3 /mnt/
Create new root subvolume @:
# btrfs subvolume create /mnt/@
# btrfs subvolume create /mnt/@home
# btrfs subvolume create /mnt/@var-log
# umount /mnt/
# mount -t btrfs -o compress=lzo,noatime,nodiratime,space_cache=v2,subvol=@ /dev/sda3 /mnt/
# btrfs subvolume create /mnt/tmp
Mount boot (=ESP)
# mkdir -p /mnt/boot
# mount /dev/disk/by-label/ESP /mnt/boot
Enable swap (just to be certain):
# swapon /dev/sda2

Create default system setup configuration files (NixOS is based on a declarativ configuration):
# nixos-generate-config --root /mnt
Customize the /*mnt/etc/nixos/configuration.nix* to suit your needs
```ini

```

