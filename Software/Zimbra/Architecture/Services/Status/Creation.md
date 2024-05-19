# Creation
Created Mittwoch 22 Januar 2020


1. Create status logs **/opt/zimbra/libexec/zmstatuslog**.
2. Started by zimbra user crontab: */2 * * * * /opt/zimbra/libexec/zmstatuslog > /dev/null 2>&1
3. This creates STATUS entries in /var/log/zimbra-stats.log.

e.g. 
Sep  5 08:34:06 mail zimbramon[27690]: 27690:info: 2019-09-05 08:34:01, STATUS: mail.example.com: memcached: Running
Sep  5 08:34:06 mail zimbramon[27690]: 27690:info: 2019-09-05 08:34:01, STATUS: mail.example.com: mta: Running
Sep  5 08:34:06 mail zimbramon[27690]: 27690:info: 2019-09-05 08:34:01, STATUS: mail.example.com: opendkim: Running
This 

4. Then swatchdog  copies it to the database
5. where the web interface reads it.


