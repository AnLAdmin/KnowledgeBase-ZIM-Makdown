# SMTP
Created Samstag 10 April 2021

[Src](https://github.com/acmesh-official/acme.sh/wiki/notify#12-set-notification-for-smtp)

Variables
---------
Mail from:	From mail address
Mail tos:	Address to send notifications to. Multiple address separated by commas.
Mail host:	SMTP host FQDN
SMTP secure:	Set if you want to send over TLS. Not set, no TLS.
 One of **none**, **ssl** (implicit TLS, TLS Wrapper), **tls** (explicit TLS, STARTTLS)


Set env variables
-----------------
export SMTP_FROM="<Mail from>"
export SMTP_TO="<Mail tos>"
export SMTP_HOST="<Mail host>"
export SMTP_SECURE="<SMTP secure>"

Initiat hook
------------
acme.sh$ acme.sh --set-notify --notify-hook smtp --notify-level  3

