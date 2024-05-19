# Check if filesystem object exists
Created Donnerstag 20 Februar 2020

[Source](\\ghome\data\Library\Information\System\Linux\Software Deployment\Ansible\How to check if a file_directory exists in Ansible - My Daily Tutorials.html)

File/directory or link exists
-----------------------------
```yaml
- hosts: all
  tasks:
  - name: Ansible check file exists example.
    stat:
      path: /Users/mdtutorials2/Documents/Ansible/prompt.yaml
    register: file_details

  - debug:
      msg: "The file or directory exists"
    when: file_details.stat.exists
```


File exists
-----------
```yaml
- hosts: all
  tasks:
  - name: Ansible check file exists example.
    stat:
      path: /Users/mdtutorials2/Documents/Ansible/prompt.yaml
    register: file_details

  - debug:
      msg: "The file or directory exists"
    when: file_details.stat.exists and file_details.stat.isreg
```


File not exists
---------------
```yaml
...
when: file_details.stat.isreg is not defined
```


Directory exists
----------------
```yaml
- hosts: all
  tasks:
  - name: Ansible check file exists example.
    stat:
      path: /Users/mdtutorials2/Documents/Ansible/prompt.yaml
    register: file_details

  - debug:
      msg: "The file or directory exists"
    when: file_details.stat.exists and file_details.stat.isdir
```


Directory not exists
--------------------
```yaml
...
when: file_details.stat.isdir is not defined
```


Link exists
-----------
```yaml
- hosts: all
  tasks:
  - name: Ansible check file exists example.
    stat:
      path: /Users/mdtutorials2/Documents/Ansible/prompt.yaml
    register: file_details

  - debug:
      msg: "The file or directory exists"
    when: file_details.stat.exists and file_details.stat.islnk
```


Link not exists
---------------
```yaml
...
when: file_details.stat.islnk is not defined
```

