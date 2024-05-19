# When
Created Montag 24 Februar 2020

[Source](https://docs.ansible.com/ansible/latest/user_guide/playbooks_conditionals.html#the-when-statement)

Comparison operators
--------------------
Uses Python operators.

Compare variables
-----------------

### Examples
```yaml
tasks:
  - name: "shut down Debian flavored systems"
    command: /sbin/shutdown -t now
    when: ansible_facts['os_family'] == "Debian"
```

```yaml
tasks:
  - name: "shut down Debian flavored systems"
    command: /sbin/shutdown -t now
    when: var1 == "Content"
```


On success
----------
```yaml
tasks:
  - <task>
	register: result
	ignore_errors: True	# optional

  - <task>
	when: result is succeeded
```


On failure
----------
```yaml
tasks:
  - <task>
	register: result
	ignore_errors: True	# optional

  - <task>
	when: result is failed
```


On skip
-------
```yaml
tasks:
  - <task>
	register: result
	ignore_errors: True	# optional

  - <task>
	when: result is skipped
```

