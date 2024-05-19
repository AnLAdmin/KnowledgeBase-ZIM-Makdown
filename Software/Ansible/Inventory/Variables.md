# Variables
Created Freitag 31 Januar 2020

Key/value pair
--------------
It is possible to set key/values pairs to hosts.

### Example

#### Ini
```ini
[atlanta]
host1 http_port=80 maxRequestsPerChild=808
host2 http_port=303 maxRequestsPerChild=909
```


#### YAML
```yaml
atlanta:
  host1:
    http_port: 80
    maxRequestsPerChild: 808
  host2:
    http_port: 303
    maxRequestsPerChild: 909
```


SSH ports
---------
Can be added like port numbers to the IP address:
<host>:<ssh port>

Vars section
------------
Everything after the = or : is part of the value for the entry.

### Example

#### Ini
```ini
[atlanta]
host1
host2

[atlanta:vars]
ntp_server=ntp.atlanta.example.com
proxy=proxy.atlanta.example.com
```


#### YAML
```yaml
atlanta:
  hosts:
    host1:
    host2:
  vars:
    ntp_server: ntp.atlanta.example.com
    proxy: proxy.atlanta.example.com
```


Organizing host and group variables
-----------------------------------
[Manual](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html#id14)

