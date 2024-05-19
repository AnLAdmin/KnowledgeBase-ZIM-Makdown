# Variables
Created Donnerstag 06 Februar 2020

[Source](https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html)

Name
----
Persists of letters, numbers and underscores. They should start with letters.

Location
--------
Can define and use them in:

* [Inventory](../Inventory.md)
* [Playbooks](./Playbooks.md)
* Includes/Imports


Dictionary
----------

### Definition
```yaml
foo:
  field1: one
  field2: two
test_var: 1568
```


### Access
Use quotes if the variable is directly after the statment.
```yaml
"{{ foo['field1'] }}"
"{{ foo.field1 }}"
"{{ test_var }}"
This is a variable {{ test_var }} # Can be withoot because it can't be mistaken with a dictionary
```


Key/Value
---------

### YAML
```yaml
<Group>:
  vars:
    ntp_server: ntp.atlanta.example.com
    proxy: proxy.atlanta.example.com
```


### Ini
```ini
[<group>:vars]
ntp_server=ntp.atlanta.example.com
proxy=proxy.atlanta.example.com
```


Usage
-----
```yaml

```

