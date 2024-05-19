# Playbooks
Created Freitag 31 Januar 2020

[Source](https://docs.ansible.com/ansible/latest/user_guide/playbooks.html)

Run a [playbook](./Playbooks/Structure.md) command which depends on a playbook file:
#|$ ansible-playbook [-i <custom [inventory](../Inventory.md) files> | "hosts, ..."] [--become --ask-become-pass] [[--become|-b --ask-become-pass|-K](./Security/Administrative_rights.md)] [-v] <playbook>

-v:		Verbose output (e.g module results)

