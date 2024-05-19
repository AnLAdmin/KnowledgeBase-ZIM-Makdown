# Create Basic Authentication user
Created Freitag 26 März 2021

Variables
---------
Config path:		Path to NGINX configuration directory
User:			Username

New user
--------
This adds a new user to the NGINX password file:
# echo -n '<User>:' >> <Config path>/.htpasswd
# openssl passwd -apr1 >> <Config path>/.htpasswd

Change user password
--------------------
Create a password:
# openssl passwd -apr1

Replace the encrypted password of the <User> in the file **<Config path>/.htpasswd**.

E.g.
# comment
name1:password1
name2:password2:comment
name3:password3

