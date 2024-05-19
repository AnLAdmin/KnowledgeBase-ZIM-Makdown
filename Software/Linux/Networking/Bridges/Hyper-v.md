# Hyper-v
Created Samstag 11 Januar 2020

Bridges need mac address spoofing
---------------------------------
Because Hyper-V switches doe not support [promiscuous mode](https://en.wikipedia.org/wiki/Promiscuous_mode) it is necessary to enable MAC spoofing.
Enable mac address spoofing in the specific VM settings:
Network Adapter - Advanced Features: Enable MAC address spoofing

