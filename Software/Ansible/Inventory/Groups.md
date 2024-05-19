# Groups
Created Donnerstag 30 Januar 2020

Default
-------
This groups don't need entries in the hosts file.

### All
This groups should not be defined. It exists implicit.
Calls all hosts in the hosts file.

### Ungrouped
All hosts which are not assinged to a group.

Custom
------

### Ini
Groups are defined with square brackets [] like sections in an ini file (ini file format)

#### Example
```ini
mail.example.com

[webservers]
foo.example.com
bar.example.com

[dbservers]
one.example.com
two.example.com
three.example.com
```


### YAML
or as YAML sections under the section **children**.

#### Example
```yaml
all:
  hosts:
	mail.example.com:
  children:
	webservers:
	  hosts:
		foo.example.com:
		bar.example.com:
	dbservers:
	  hosts:
		one.example.com:
		two.example.com:
		three.example.com:
```


Groups Nesting
--------------
[Manual](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html#id13)


