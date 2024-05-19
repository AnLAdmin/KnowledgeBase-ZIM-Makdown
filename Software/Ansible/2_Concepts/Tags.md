# Tags
Created Donnerstag 20 Februar 2020

[Source](https://docs.ansible.com/ansible/latest/user_guide/playbooks_tags.html)

Mark a task with a, well, tag.
You can call tagged task with command line arguments.

Syntax
------

### Variant 1
```yaml
- ...
  tags:
    - <tag>
    - <tag>
    - ...
```


### Varaint 2
```yaml
- ...
  tags: <tag>
```


### Variant 3

```yaml
- ...
  tags: [ <tag>, <tag>, ... ]
```


Special tags
------------

### always
This will always run a task, unless specifically skipped (--skip-tags always)
-> Fact gathering is tagged with it by default.

### never
This will never run a task, unless it's tag (includes never) is specifically requested.

Start playbook tasks with tag(s)
--------------------------------
$ ansible-playbook <playbook> --tags "<tag>,<tag>,..."

### Examples
$ ansible-playbook example.yml --tags "configuration,packages"

Start playbook tasks which have not this tag(s)
-----------------------------------------------
$ ansible-playbook <playbook> --skip-tags "<tag>,<tag>,..."

### Examples
$ ansible-playbook example.yml --skip-tags "packages"

List tags for a playbook
------------------------
$  ansible-playbook <playbook> --list-tags

List tasks associaated with tags
--------------------------------
$  ansible-playbook <playbook> --tags "<tag>,..." --list-tags

