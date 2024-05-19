# IP forwarding
Created Freitag 24 Januar 2020

Packet forwarding between Linux hists network interfaces which is by **default disabled**.

IPv4
----

### Check status
# sysctl net.ipv4.ip_forward
or
# cat /proc/sys/net/ipv4/ip_forward

### Enable/Disable

#### temporarly
# sysctl -w net.ipv4.ip_forward=1|0
or
# echo 1|0 | /proc/sys/net/ipv4/ip_forward

#### permanently
Edit /etc/sysctl.conf:
```ini
net.ipv4.ip_forward = 1|0
```

# sysctl -p /etc/sysctl.conf
or
# service network restart
or (Ubuntu)
# /etc/init.d/procps restart

IPv6
----

### Check status
# sysctl net.ipv6.conf.all.forwarding
or
# cat /proc/sys/net/ipv6/conf/all/forwarding

### Enable/Disable

#### temporarly
# sysctl -w net.ipv6.conf.all.forwarding=1|0
or
# echo 1|0 | /proc/sys/net/ipv6/conf/all/forwarding

#### permanently
Edit /etc/sysctl.conf:
```ini
net.ipv6.conf.all.forwarding=1|0
```

# sysctl -p /etc/sysctl.conf
or
# service network restart
or (Ubuntu)
# /etc/init.d/procps restart

