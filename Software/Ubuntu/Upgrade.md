# Upgrade
Created Samstag 25 Juni 2022

Before distribution upgrade run:
# apt update && apt full-upgrade && apt autoremove && apt autoclean
# reboot

Check SW installed from a PPA and if there is something to do before update:
# ll /etc/apt/sources.list.d/
**-> During an Ubuntu upgrade PPAs get disabled!**

Do some services need stopping before the upgrade? (E.g. containers)

Upgrade system:
# do-release-upgrade

If the available version is still the first release without minor e.g 22.04 than 22.04.1 you have to add -d to the above cmmand.
-> ATTENTION: Because you are going to install the first release of a mayor release it will still contain a lot of bugs.

Upgrade manually the configuration files where necessary. See also the subpages here for notes.

