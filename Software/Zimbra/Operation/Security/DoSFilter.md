# DoSFilter
Created Donnerstag 23 Januar 2020

[Manual](https://wiki.zimbra.com/wiki/DoSFilter)

zimbraHttpDosFilterDelayMillis
------------------------------
Default: -1
Delay imposed on all requests over the *zimbraHttpDosFilterMaxRequestsPerSec* value.
-1 = Reject request, 0 = No delay, any other value = Delay in ms
e.g. 
# su -zimbra -c "zmprov mcf zimbraHttpDosFilterDelayMillis 20"

zimbraHttpDosFilterMaxRequestsPerSec
------------------------------------
Default: 30
Requests in excess of this are throttled with the value of zimbraHttpDosFilterDelayMillis.
# su -zimbra -c "zmprov mcf zimbraHttpDosFilterMaxRequestsPerSec 200"

zimbraInvalidLoginFilterDelayInMinBetwnReqBeforeReinstating
-----------------------------------------------------------
Default: 15
Time before the throttle is lifted and the last request.
e.g. 
# su -zimbra -c "zmprov mcf zimbraInvalidLoginFilterDelayInMinBetwnReqBeforeReinstating 30"

zimbraInvalidLoginFilterMaxFailedLogin
--------------------------------------
Default: 10
The number of failed logins before an IP is delayed/blocked besed on *zimbraHttpDosFilterDelayMillis*.
e.g. 
# su -zimbra -c "zmprov mcf zimbraInvalidLoginFilterMaxFailedLogin 10"

zimbraInvalidLoginFilterReinstateIpTaskIntervalInMin
----------------------------------------------------
Default: 5
Time until the last failed login before block is lifted.
e.g. 
# su -zimbra -c "zmprov mcf zimbraInvalidLoginFilterReinstateIpTaskIntervalInMin 5"

zimbraHttpThrottleSafeIPs
-------------------------
Default: ""
This IPs are safed from throttle.
Replace current IPs:
e.g. 
# su -zimbra -c "zmprov mcf zimbraHttpThrottleSafeIPs 10.1.2.3/32 zimbraHttpThrottleSafeIPs 192.168.4.0/24"
Add to current IPs:
e.g.
# su -zimbra -c "zmprov mcf +zimbraHttpThrottleSafeIPs 10.1.2.3/32"
# su -zimbra -c "zmprov mcf +zimbraHttpThrottleSafeIPs 192.168.4.0/24"
Check settings with:
# grep -i "DoSFilter: Configured whitelist IPs" /opt/zimbra/log/mailbox.log

