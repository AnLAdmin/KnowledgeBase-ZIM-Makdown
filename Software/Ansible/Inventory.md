# Inventory
Created Freitag 31 Januar 2020

[Source](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html#intro-inventory)

Default
-------
Location (default): /etc/ansible/hosts
The inventory (Ini format or expandable with inventory plugins like YAML) holds the managed hosts. One can group those hosts. The ansible commands or playbook chooses the hosts to act on with  a pattern from the inventory.
E.g.
$ ansible -m <module> [-a <optional module argument>] <host/host group pattern>
Uses the defalut inventory (no option -i) with the function module <module> for <host/host group pattern>.

Custom
------
Can be defined with the option **-i** as *file* or as *quoted comma/-separated list* on the command line.

### File
E.g.
$ ansible __-i ~/hosts__-m <module> [-a <optional module argument>] <host/host group pattern>
Uses the hosts in the **file ~/hosts**.

### Command line list
E.g.
$ ansible __-i "localhost,<PC name>,"__-m <module> [-a <optional module argument>] <host/host group pattern>
Uses the hosts listed on the command line in list **"localhost,<PC name>,"**.

Multiple inventory sources
--------------------------
[Manual](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html#id16)

