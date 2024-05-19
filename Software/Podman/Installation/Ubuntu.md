# Ubuntu
Created Dienstag 14 Juli 2020

[Source](https://podman.io/getting-started/installation)

20.04
-----
$ sudo apt-get -y update
$ sudo apt-get -y install podman

18.04
-----
Create variables:
# . /etc/os-release
Add libcontainers repository:
# echo "deb <https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_${VERSION_ID}/> /" | tee /etc/apt/sources.list.d/devel:kubic:libcontainers:stable.list
# wget -qO - <https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_${VERSION_ID}/Release.key> | apt-key add -
**Optionally** wirth curl:
curl -L <https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_${VERSION_ID}/Release.key> | apt-key add -

Install podman:
# apt-get update -qq
Minimal -> Does not support rootless:
# apt-get -qq -y install podman --no-install-recommends
For rootless:
# apt-get -qq -y install podman


