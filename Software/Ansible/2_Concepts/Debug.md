# Debug
Created Montag 24 Februar 2020

Show variable content
---------------------
```yaml
- name: Ansible Variable Example Playbook
  hosts: app
  tasks:
  
    # display the variable data type
    - debug:
    	msg: "{{ <var> }}"
```

