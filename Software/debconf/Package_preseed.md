# Package preseed
Created Montag 24 Februar 2020

This will ask for the settings again by a gui wizard (frontend default) and stores the answers in the [database](./Database.md).
# dpkg-reconfigure <package name>

On the machine already installed. This reads all the in the [database](./Database.md) stored settings to a text file.-> debconf-get-selections need *debconf-utils* installed. ([Src](https://wiki.debian.org/PackageManagement/Preseed))
$ debconf-get-selections | grep "^<package name>"> conf.txt
Configure the new machine.
$ debconf-set-selections <conf.txt
$ Apt-get install <package name>

Dependencies
------------
Package:		debconf-utils

