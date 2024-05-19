# Structure
Created Mittwoch 05 Februar 2020

A playbook is comprised of hosts, tasks,handlers and variables.

Hosts
-----
Defined in [inventories](../../Inventory.md).

### Syntax
```yaml
hosts: <patterns>
```

pattern: [Hosts](../../Inventory/Hosts.md)

Tasks
-----
A job to be done.  Mostly executed by an ansible module.

### Syntax
```yaml
tasks:
  - name <text>
  	<module name>:
  	  <Arguments>
  	  ...
```


Handlers
--------
[Handlers](https://docs.ansible.com/ansible/latest/user_guide/playbooks_intro.html#handlers-running-operations-on-change) are called after a block of tasks. The **notify** statement informs the hadler to act. It's executed **once**. -> It can get more than on notification.
They er called in order of their definition not their order in notify.

Variables
---------
Can also be defined in playbooks not only in the [Inventory](../../Inventory/Variables.md) (or directories).
Use section **vars:**.

Examples
--------
```yaml
- hosts: webservers
  vars:
    http_port: 80
```

