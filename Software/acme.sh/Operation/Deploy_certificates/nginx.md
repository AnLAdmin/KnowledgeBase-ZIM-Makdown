# nginx
Created Freitag 06 November 2020

Variables
---------
FQDN:			DNS Full Qualidied Domain Name.
Path to certificates:	Location of the Nginx certificate location
Command:		Command to prepare and/or refresh the applications configuration
Service name FQDN:	DNS name to host/container

Deploy
------
As *acme.sh* (prefered) user or root:
$ su - acme.sh
$ acme.sh --install-cert \
-d <FQDN> \
--key-file <Path to <certificates>/<FQDN>.key \
--fullchain-file <certificates>/<FQDN>.chained.cer \
[--reloadcmd "<Command>"]

No **reloadcmd** for container. That has to be done by other means.

### E.g
acme.sh --install-cert \ 
-d '<Service name FQDN>' \
--key-file '/srv/container/@nginx/data/etc/Certificates/<Service name FQDN>.key' \
--fullchain-file '/srv/container/@nginx/data/etc/Certificates/<Service name FQDN>.chained.cer'


