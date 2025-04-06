# Apllication profiles
Created Sonntag 15 Dezember 2024

Defaults
--------
You can use the names listed in the file /etc/services as app names.
### Example
$ cat /etc/services | grep spamd
spamd           783/tcp                         # spamassassin daemon
# ufw allow spamd

Custom
------
You can create this profiles in ``/etc/ufw/applications.d/``. Use the titles as the profiles file name.

incus
-----
```ini
[Incus API]
title=Incus API
description=Incus server API
ports=8443/tcp
```
openssh-server
--------------
```ini
[OpenSSH]
title=Secure shell server, an rshd replacement
description=OpenSSH is a free implementation of the Secure Shell protocol.
ports=22/tcp
```
postfix
-------
```ini
[Postfix]
title=Mail server (SMTP)
description=Postfix is a high-performance mail transport agent
ports=25/tcp

[Postfix SMTPS]
title=Mail server (SMTPS)
description=Postfix is a high-performance mail transport agent
ports=465/tcp

[Postfix Submission]
title=Mail server (Submission)
description=Postfix is a high-performance mail transport agent
ports=587/tcp
```
rdp
---
```ini
[RDP]
title=RDP
description=Remote Desktop Protocol
ports=3389/tcp
```

