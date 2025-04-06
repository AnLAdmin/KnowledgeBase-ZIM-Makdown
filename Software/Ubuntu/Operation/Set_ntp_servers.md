# Set ntp servers
Created Sonntag 07 Juli 2024

By systemd
----------
### Get current time serveres
$ timedatectl show-timesync

### Activate NTP sync
# timedatectl set-ntp true

### Set time servers
Create acopy of **/etc/systemd/timesyncd.conf** to **/etc/systemd/timesyncd.conf.d/**:
``# cp`` **``/``**``etc/systemd/timesyncd.conf /etc/systemd/timesyncd.conf.d/<Name of config>``

Uncomment settings in the created file and set some servers (space separated) in the line **NTP=** and **FallbackNTP=**:
```sh
[Time]
NTP=<Server 1> <Server 2> ...
FallbackNTP=ntp.ubuntu.com
RootDistanceMaxSec=5
PollIntervalMinSec=32
PollIntervalMaxSec=2048
ConnectionRetrySec=30
SaveIntervalSec=60
```
You can choose servers from [here](https://gist.github.com/mutin-sa/eea1c396b1e610a2da1e5550d94b0453) or [ntp pool](https://www.ntppool.org/en/).
**But if it is important that all your devices have the exact same time (and drift)** use or setup a local time server.

Restart time sync service:
# systemctl restart systemd-timesyncd

