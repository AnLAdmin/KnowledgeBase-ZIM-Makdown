# Tasklist
Created Montag 24 Februar 2020

[Source](https://docs.ansible.com/ansible/latest/user_guide/playbooks_intro.html#tasks-list)

```yaml
tasks:
  - name: <task description>
    <module>:
    	...
```


* Executed in order
* All tasks per host
* Failed task interrupts the task list execution for the current host and skips to the next host


