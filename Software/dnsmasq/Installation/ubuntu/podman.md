# podman
Created Samstag 14 November 2020

Only use for Podman
-------------------
Disable dnsmasq service:
# systemctl disable dnsmasq.service

### Reason
Gets in conflict with systemd-resolve. We don't need the service for podman networks. They start their separate instance with its own configuration.

