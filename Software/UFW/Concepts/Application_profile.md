# Application profile
Created Samstag 23 November 2024

UFW application profiles are definition files with a list/range of network ports an application needs. The files are located in **/etc/ufw/applications.d**.

Structure
---------
The file is in the a simple INI format. Is can contain multiple application definitions.
```ini
[<Application name>]
title=<App title>
description=<App description>
ports=<Ports>

[<Application 2 name>]
..
```

Application name	App name, can contain spaces. Use it with double qoutes in the commands.
App title		App nice name, can contain spaces.
Port			TCP/IP ports separated by a bar (|). *Multiple* port numbers can be given separated by a comma or as *port number range* with a double point (:).
Syntax: <Port number>[,<Port number>][[,]<Port number>:<Port number>][/<Protocol]|...

### Example
Random example
```ini
[Some Service]
title=Some title
description=Some description
ports=12/udp|34|56,78:90/tcp
```

Postfix (MTA) ports, /etc/ufw/applications.d/postfix
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
```


