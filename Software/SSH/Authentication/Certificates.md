# Certificates
Created Montag 27 Januar 2020

Variables
---------

Host name:		Name of hosts (NOT FQDN)
DNS domain:		DNS domain for the signing CA (domain.tld)
User name:		What ever you like to use as user identifier (e.g. name, login, mail address, ...)
User short name:	<User name> abbreviation **without** spaces (login name/Linux user name)

Host Certificates
-----------------

### Create CA host key pair
Generate different key pair types to identify the CA host. ED25519 is the safest and is preferred here.
$ ssh-keygen -t ed25519 -C "Host Certification Authority <DNS domain> (ed25519)" -f ca_host_ed25519_<DNS domain>
$ ssh-keygen -t rsa -b 4096 -C "Host Certification Authority <DNS domain> (RSA 4096)" -f ca_host_rsa_<DNS domain>
$ ssh-keygen -t ecdsa -b 521 -C "Host Certification Authority <DNS domain> (ecdsa 521)" -f ca_host_ecdsa_<DNS domain>

#### Add CA host public key to all hosts
Create file **ssh_known_hosts**:
$ echo "@cert-authority *.<DNS domain> `cat ca_host_ed25519_<DNS domain>.pub`" >ssh_known_hosts
$ echo "@cert-authority * `cat ca_host_ed25519_<DNS domain>.pub`" >>ssh_known_hosts

The **ssh_known_hosts** file must be installed on all hosts of <DNS domain>.
In **/etc/ssh**:
cp ssh_known_hosts /etc/ssh

### Create host keys
Depending on the key type, use **-t rsa -b 4096**, **-t ecdsa -b 521** or **-t ed25519**.
$ ssh-keygen -t ed25519 -C <Host name>.<DNS domain> -f <Host name>_ed25519

### Sign host public keys
For security reasons, the certificates (signatures) created should only be valid for **4 weeks** and should normally be updated in a timely manner using a cron job.
$ ssh-keygen -s ca_host_ed25519_<DNS domain> -I <Host name> [-n <Host name>.<DNS domain>[, ...]] -h -V +4w <Host name>_ed25519

### Install host keys
On hosts in /etc/ssh:
$ cp <Host name>_ed25519 /etc/ssh/ssh_host_ed25519_key
$ cp <Host name>_ed25519.pub /etc/ssh/ssh_host_ed15519_key.pub
$ cp <Host name>_ed25519-cert.pub /etc/ssh/ssh_host_ed25519_key-cert.pub

The **/etc/ssh/sshd_config** on the hosts must contain the following entry:
```ini
HostCertificate /etc/ssh/ssh_host_ed25519_key-cert.pub
```


User Certificates
-----------------

### Create user CA
Generate different key types. ED25519 is the safest and is preferred here.
$ ssh-keygen -t ed25519 -C "User Certification Authority <DNS domain> (ed25519)" -f ca_user_ed25519_<DNS domain>
$ ssh-keygen -t rsa -b 4096 -C "User Certification Authority <DNS domain> (rsa 4096)" -f ca_user_rsa_<DNS domain>
$ ssh-keygen -t ecdsa -b 521 -C "User Certification Authority <DNS domain> (ecdsa 521)" -f ca_user_ecdsa_<DNS domain>

The CA user public key must be installed on all hosts of <DNS domain>.
In **/etc/ssh**:
$ cp ca_user_ed25519_<DNS domain>.pub /etc/ssh/ca_ed25519_user_key.pub

Die **/etc/sshsshd_config** auf dem Server muss folgenden Eintrag beinhalten:
```ini
TrustedUserCAKeys /etc/ssh/ca_ed25519_user_key.pub
```


### Create user key pairs
**ATTENTION: This should normally be done by the user themselves.** 
Depending on the key type, use "-t rsa -b 4096", "-t ecdsa -b 521" or "-t ed25519".
$ ssh-keygen -t ed25519 -C "<User name>" -f <User short name>_ed25519

### Sign user public keys
For security reasons, the certificates created should only be valid for **4 weeks** and should normally be updated in a timely manner using a cron job. The “Principals” in the “-n” option specify which user can log in with this certificate.
$ ssh-keygen -s ca_ed25519_user -I <User name> -n <User short name>,root -V +4w <User short name>_ed25519

### Install user keys
In /etc/ssh:
$ cp <User short name>_ed25519 /home/<User short name>/.ssh/id_ed25519
$ cp <User short name>_ed25519.pub /home/<User short name>/.ssh/id_ed25519.pub
$ cp <User short name>_ed25519-cert.pub /home/<User short name>/.ssh/id_ed25519-cert.pub

### Revoke user key
Add all public keys you want to revoke:
$ cat <User short name>_ed25519.pub >>revoked_keys

Copyrevocation list to hosts **/etc/ssh**:
$ cp revoked_keys /etc/ssh/revoked_keys

Die sshd_config auf dem Server muss folgenden Eintrag beinhalten:
```ini
RevokedKeys /etc/ssh/revoked_keys
```



