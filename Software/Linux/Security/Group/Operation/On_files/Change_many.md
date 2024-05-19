# Change many
Created Mittwoch 29 Juli 2020

# for i in `find <path> -group <old GID>`; do chgrp <new GID> $i; done
or
# find <path> -group <old GID> -exec chgrp -h <group name> {} \;
-> This assumes the group already has the new group id (in /etc/group) [set](../Change_ID.md).

