# Ubuntu
Created Samstag 11 Januar 2020

Prerequisite
------------

### Virtual machines

#### Hyper-V
The uplink interface (Hyper-V nic) to the bridge needs [mac address spoofing](../../Linux/Networking/Bridges/Standard/Hyper-v.md) enabled.

Installation
------------

### Apt
Install lxd:
$apt install lxd

### Snap
For the newest versions.
$ snap install lxd
-> Snap can have special begavior because it is like a sandboxed app. E.g uses vim to edit profiles -> switching editor via export EDITOR=nano only helps if the editor is in the snap package.


