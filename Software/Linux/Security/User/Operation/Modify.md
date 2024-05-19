# Modify
Created Sonntag 26 Januar 2020

To modify an existing user one can use the command usermod or edit /etc/passwd directly.

Change shell
------------
$ usermod --shell /path/to/shell <user> 
E.g.
$ usermod --shell /bin/bash hmeier

