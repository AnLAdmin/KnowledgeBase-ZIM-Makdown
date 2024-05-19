# Ad-hoc commands
Created Samstag 25 Januar 2020

[Source](https://docs.ansible.com/ansible/latest/user_guide/intro_adhoc.html)

An Ansible ad-hoc command uses the /usr/bin/ansible command-line tool to automate a single task on one or more managed nodes.
This commands are run with the command :
#|$ ansible [-i <custom [inventory](../Inventory.md) files> | "hosts, ..."] -m <[module](../Modules.md)> [-a <additional module specific arguments] [[--become|-b --ask-become-pass|-K](./Security/Administrative_rights.md)] <hosts pattern>



