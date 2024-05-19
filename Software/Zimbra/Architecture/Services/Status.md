# Status
Created Mittwoch 22 Januar 2020

Query with logging
------------------
# su - zimbra -c "/opt/zimbra/libexec/zmstatuslog"
-> Creates STATUS entries in  /var/log/zimbra-stats.log
# grep STATUS /var/log/zimbra-stats.log

Query with zmcontrol
--------------------
# su - zimbra -c "zmcontrol status"

Query with soap
---------------
zmsoap -z GetServiceStatusRequest


