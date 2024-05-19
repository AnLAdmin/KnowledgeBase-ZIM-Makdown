# Create
Created Samstag 25 Januar 2020

Use **useradd **-> adduser despite more userfriendly can't add to multiple groups.

Default for sudo user
---------------------
# useradd -c "<user's full name>" -s /bin/bash -m --groups sudo,adm,cdrom,plugdev,netdev <login name>

Default for normal user
-----------------------
# useradd -c "<user's full name>" -s /bin/bash -m --groups <additional groups> <login name>
-> Default user group with login name is created.

### with specific user id
# useradd -c "<user's full name>" -s /bin/bash -m --groups <additional groups> **-u <UID>** <login name>

System user
-----------
# useradd -c "<user's full name>" -r --groups <additional groups> <login name>

### specific UID
Add an UID inside a custom (non default) given range.
# useradd -c "<user's full name>" -r -K SYS_UID_MIN=<new start> -K SYS_UID_MAX=<new end> --groups <additional groups> <login name>
-K: Overwrites the defaults in /etc/login.defs.

