# Test encryption
Created Mittwoch 14 April 2021

$ openssl s_client -connect <URL without protocaol>:<Port> -tls1_2|-tls1_3

### Examples
$ openssl s_client -connect <Service name FQDN>:443 -tls1_3

