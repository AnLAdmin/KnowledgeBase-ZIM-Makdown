# Linux
Created Samstag 05 September 2020

Installation & configuration
----------------------------

If the UrBackup server options Autoupdate clients and Download client from update server this is only needed the first time.

Start Linux UrBackup client installation with (Change the version in the command according the correct client version):
# ubver=**<ENTER VERSION>** TF=`mktemp` && wget "<https://hndl.urbackup.org/Client/${ubver}/UrBackup%20Client%20Linux%20${ubver}.sh>" -O $TF && sh $TF; rm $TFub
__With curl:__
# ubver=**<ENTER VERSION>** TF=`mktemp` && curl -o $TF "<https://hndl.urbackup.org/Client/${ubver}/UrBackup%20Client%20Linux%20${ubver}.sh>" && sh $TF; rm $TF
__Beta client path:__ <http://beta.urbackup.org/Client/><ENTER VERSION>%20beta/UrBackup%20Client%20Linux%20<ENTER VERSION>%20beta.sh
Proceed with installation: <ENTER>
Choose snapshot mechanism: 3 <ENTER> (btrfs snapshots)


### Configure local firewall

#### Configure firewall (ufw)
Ubuntu uses ufw as local firewall.
Create application profile file **/etc/ufw/applications.d/urbackupclt** for urBackup Server:
```ini
[urBackup Client]
title=urBackup client
description=Client rules incoming. UrBackup is an easy to setup Open Source client/server backup system.
ports=35621,35623/tcp|35622/udp
```

Update application profile list (Optionally if new):
$ ufw app update 'urBackup Client'
Activate urBackup rules/profile:
$ ufw allow from <IP to backup server> to any app 'urBackup Client'
Enable ufw (ufw status to check state) if necessary:
$ ufw enable
Check ufw status:
$ ufw status

### Reconnect client with UrBackup server
If the UrBackup Server was replaced you need to reconnect the already installed clients:
Delete  /usr/local/var/urbackup/session_idents.txt.
Restart the UrBackup client service:
$ systemctl restart urbackupclientbackend.service

Over server
-----------

### Get new installation sources
One needs <https://github.com/ptempier/get_urbackupclient/blob/master/updateclient.sh> downloaded and executable:
$ wget <https://raw.githubusercontent.com/ptempier/get_urbackupclient/master/updateclient.sh>
$ chmod 744 updateclient.sh
Start download:
$ updateclient.sh '<Version>' 
E.g.
$ updateclient.sh '2.0.34'
$ updateclient.sh '2.1.4%20beta'

