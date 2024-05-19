# Patterns
Created Dienstag 04 Februar 2020

[Source](https://docs.ansible.com/ansible/latest/user_guide/intro_patterns.html)

A pattern chooses the [host](./Hosts.md)(s) or group of [hosts](./Hosts.md) (or excludes) on which ansible will act.

Common patterns
---------------
All hosts:			all (or *)
One host:			host1 -> as listed in the [inventory](../Inventory.md)
Multiple hosts:			host1:host2 (or host1,host2)
One group:			webservers
Multiple groups:		webservers:dbservers (or webservers,dbservers) 	-> all hosts in webservers plus all hosts in dbservers
Excluding groups:		webservers:!atlanta 				-> all hosts in webservers except those in atlanta
Intersection of groups:		webservers:&staging				-> any hosts in webservers that are also in staging

__Escape & and ! one command line.__

Wildcards
---------
E.g.
192.0.\*
\*.example.com
\*.com

You can mix them with common patterns:
one*.com:dbservers

