# Ubuntu
Created Sonntag 14 August 2022

Uninstall Zimbra DNS-Cache
--------------------------
# su - zimbra
$ zmdnscachectl stop
$ zmprov ms `zmhostname` -zimbraServiceEnabled dnscache
$ zmprov ms `zmhostname` -zimbraServiceInstalled dnscache
$ exit
# apt-get remove zimbra-dnscache zimbra-dnscache-components zimbra-dnscache-base
# su - zimbra
$ zmcontrol start

