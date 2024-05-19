# Basic
Created Freitag 26 März 2021

Variables
---------
Config path:		Path to NGINX configuration directory
Site name:		Name of the site to access

Create NGINX password file
--------------------------
# touch <Config path>/.htpasswd

Container (optionally)
----------------------
Change access rights accordingly.

Configure site
--------------
Add the following to site configuration file <Config path>/conf.d/sites-available/<Site name>:
```js
    # Node-RED dashboard node
    location /ui/ {
        auth_basic "Node-RED Dashboard is restricted!";
        auth_basic_user_file /etc/nginx/.htpasswd;

        resolver 10.11.0.1 ipv6=off;
        set $upstream_endpoint http://node-red:1880;

        proxy_pass $upstream_endpoint;

        proxy_set_header X-Real-IP $remote_addr;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
    }

```

[Reload](../../Operation/Reload_configuration.md) configuration.

### For Container
Add the configuration file to the container-cli (/service file) command and restart the container.

