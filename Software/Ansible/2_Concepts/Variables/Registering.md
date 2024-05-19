# Registering
Created Samstag 08 Februar 2020

This is to use task results in later tasks as variables.


* Use the statement **register:** in a playbook task.
* Modules docummentation contain a RESULT section.
* You can see the values for aparticular task if you **run a playbook** with **-v**.


Example
-------
```yaml
- hosts: web_servers

  tasks:

     - shell: /usr/bin/foo
       register: foo_result
       ignore_errors: True

     - shell: /usr/bin/bar
       when: foo_result.rc == 5
```

On success/failure/skip

