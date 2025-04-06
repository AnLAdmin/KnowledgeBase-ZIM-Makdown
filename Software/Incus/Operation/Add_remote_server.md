# Add remote server
Created Sonntag 24 November 2024

Add a remote Incus server to which you want to issue commands with the token you got while [adding the client](./Add_trusted_client.md) as trusted. Based on the given name the Incus client will look for the remote server on the network. This will add the server by his IP.
``$ incus remote add <Remote server name> <Token>``
### Example
``$ incus remote add Venus I6IjM0YWUwNWY3NmfbmFtZSI6IkImFkZHJl...``
+---------------------+------------------------------------+---------------+-------------+--------+--------+--------+
|        NAME         |                URL                 |   PROTOCOL    |  AUTH TYPE  | PUBLIC | STATIC | GLOBAL |
+---------------------+------------------------------------+---------------+-------------+--------+--------+--------+
| Venus               | ``https://192.168.0.19:8443``       | incus         | tls         | NO     | NO     | NO     |
+---------------------+------------------------------------+---------------+-------------+--------+--------+--------+

Add remote with DNS name
------------------------
This adds the remote server by DNS name and not IP address.
``$ incus remote add <Remote name> <Remote server FQDN> [--accept-certificate] --token <Token>``
--accept-certificate	Without you need to acknowledge the certificate

### Example
+---------------------+------------------------------------+---------------+-------------+--------+--------+--------+
|        NAME         |                URL                 |   PROTOCOL    |  AUTH TYPE  | PUBLIC | STATIC | GLOBAL |
+---------------------+------------------------------------+---------------+-------------+--------+--------+--------+
| Venus               | ``https://venus.domain.tld:8443``   | incus         | tls         | NO     | NO     | NO     |
+---------------------+------------------------------------+---------------+-------------+--------+--------+--------+

Add remote by URL
-----------------
To add by URL allows to specify the port. URL for remote must be HTTPS (https://).
``$ incus remote add Venus`` [``https://venus.domain.tld:8888``](https://venus.domain.tld:8888) ``[--accept-certificate] --token <Token>``
--accept-certificate	Without you need to acknowledge the certificate with **yes**.

