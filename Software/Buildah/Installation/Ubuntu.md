# Ubuntu
Created Freitag 17 Juli 2020

[Source](https://github.com/containers/buildah/blob/master/install.md)

18.04
-----
Create variables:
. /etc/os-release
Add libcontainers (if not already done with [podman installation](../../Podman/Installation/Ubuntu.md)) repository:
# sh -c "echo 'deb <http://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/x${ID^}_${VERSION_ID}/> /' > /etc/apt/sources.list.d/devel:kubic:libcontainers:stable.list"
# wget -qO - <https://download.opensuse.org/repositories/devel:kubic:libcontainers:stable/x${ID^}_${VERSION_ID}/Release.key> | apt-key add -

Install podman:
# apt update -qq
# apt -qq -y install buildah



