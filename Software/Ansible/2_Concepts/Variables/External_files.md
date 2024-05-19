# External files
Created Samstag 08 Februar 2020

You can define variables in a separated variables file and include it in a playbook.
Use the statement **vars_files:**.

Example
-------
```yaml
- hosts: all
  remote_user: root
  vars:
    favcolor: blue
  vars_files:
    - /vars/external_vars.yml

  tasks:
  - name: this is just a placeholder
    command: /bin/echo foo
```

Variables file:
```yaml
---
# in the above example, this would be vars/external_vars.yml
somevar: somevalue
password: magic
```

