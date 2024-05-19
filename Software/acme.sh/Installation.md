# Installation
Created Mittwoch 28 Oktober 2020

Variables
---------
User name:		User name to execute acme.sh script with
Group name:		Group name of the acme.sh script user
App path:		Path to acme.sh script/files
Configuration path:	Path to acme.sh configuration
Certificates path:	Path to acme.sh issued certificates (prefferable <Configuration path>/<Certificates path>)
Account mail:		Mail for acme.sh account
Logs:			Path to acme.sh logs

Create acme user
----------------
# groupadd --system <Group name>
# useradd --system -c "Let's encrypt certificate management" -M -d /nonexistent -r -s /usr/sbin/nologin -g <Group name> <User name>

Create directories
------------------
# mkdir <App path> <Configuration path> <Certificates path> <Logs>
# chown -R <User name>:<Group name> <App path> <Configuration path> <Logs>
# chmod -R 0770 <App path> <Configuration path> <Logs>

Installation
------------
[Src](https://github.com/acmesh-official/acme.sh/wiki/How-to-install)
# su - <User name>
$ cd ~
$ wget <https://github.com/acmesh-official/acme.sh/archive/master.zip>
$ unzip master.zip
or # git clone <https://github.com/Neilpang/acme.sh.git> 
$ cd acme.sh-master
or $ acme.sh
$ ./acme.sh --install \
--home <App path> \
--config-home <Configuration path> \
--certhome <Certificates path> \
--accountemail "<Account mail>"

Close console -> an alias acme.sh was created in the install users ~\.bashrc.

Edit <User name> crontab -u  to:
```ini
# Edit this file to introduce tasks to be run by cron.
#
# Each task to run has to be defined through a single line
# indicating with different fields when the task will be run
# and what command to run for the task
#
# To define the time you can provide concrete values for
# minute (m), hour (h), day of month (dom), month (mon),
# and day of week (dow) or use '*' in these fields (for 'any').
#
# Notice that tasks will be started based on the cron's system
# daemon's notion of time and timezones.
#
# Output of the crontab jobs (including errors) is sent through
# email to the user the crontab file belongs to (unless redirected).
#
# For example, you can run a backup of all your user accounts
# at 5 a.m every week with:
# 0 5 * * 1 tar -zcf /var/backups/home.tgz /home/
#
# For more information see the manual pages of crontab(5) and cron(8)
#
# m h  dom mon dow   command

0 0 * * * "/opt/acme.sh"/acme.sh --cron --home "/opt/acme.sh" --config-home "/etc/acme.sh" --force-color > /dev/null

```


### OPTIONAL: Existing account
Copy existing **account.conf** and **account.key** to <Certificates path>. And change settings if necessary.

### Configure log
Uncomment and set log path in account.conf:
```ini
LOG_FILE="/var/log/acme.sh/acme.sh.log"
```


### Set log rotate configuration
Create file /etc/logrotate.d/**acme.sh**:
```ini
var/log/acme.sh/acme.sh.log {
    weekly
    missingok
    rotate 52
    compress
    delaycompress
    notifempty
    create 0660 acme.sh acme.sh
}

```


### Configure SMTP hook
[Configure](./Installation/Notify_hook/SMTP.md) hook.

