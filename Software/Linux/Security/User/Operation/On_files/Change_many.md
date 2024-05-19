# Change many
Created Mittwoch 29 Juli 2020

root@kerneltalks # for i in `find <path> -user <old UID>`; do chown <new UID> $i; done
or
root@kerneltalks # find <path> -user <old UID> -exec chown -h <user name> {} \;
-> This assumes the user already has the new user id (in /etc/passwd) [set](../Change_ID.md).

