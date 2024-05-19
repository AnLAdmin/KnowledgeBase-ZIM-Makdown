# Forwarding
Created Freitag 28 August 2020

Act as backup (e.g. secondary) mail server for another mail domain. ([Src](https://wiki.zimbra.com/wiki/Managing_Domains))

Create forwarding mail domain
-----------------------------
Open Management console.
Click Create Domain....
Domain name: <backup mail domain>
Inbound SMTP host name: <backup SMTP host name>
Description: <backup mail description>
Next
Mail Server: <FQDN mail server>
Next
Next
Finish

Actually configure forwarding mail domain to be forwarded
---------------------------------------------------------
Change to zimbra user.
zimbra$ zmprov md <DNS domain name> zimbraMailCatchAllAddress @<DNS domain name>
zimbra$ zmprov md <DNS domain name> zimbraMailCatchAllForwardingAddress @<DNS domain name>
zimbra$ zmprov md <DNS domain name> zimbraMailTransport smtp:<Receiving SMTP server FQDN>

DNS domain name:		Name of DNS domain which uses our server as 2nd MX record / SMPT server (e.g. domain.tld)
Receiving SMTP server FQDN:	SMTP server which to send all mails for the forwareded DNS domain name (e.g. smtp.domain.tld)

zimbra$ postfix reload



