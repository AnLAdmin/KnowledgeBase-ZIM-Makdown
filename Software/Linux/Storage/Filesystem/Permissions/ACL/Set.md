# Set
Created Donnerstag 30 Januar 2020

Set permissions
---------------

### Group
$ setfacl -m g:<group>:<permissions> <path to file or directory>
e.g.
$ setfacl -m g:testusers:r /appdir

### User
$ setfacl -m u:<user>:<permissions> <path to file or directory>

Set permissions recursively
---------------------------
$ setfacl -__R__m g:<group>:<permissions> <path to file or directory>
e.g.
$ setfacl -Rm g:testusers:r appdir/

Set permissions to inherit
--------------------------
setfacl -__d__m g:<group>:<permissions> <path to file or directory>
e.g.
$ setfacl -dm g:testusers:r appdir/

