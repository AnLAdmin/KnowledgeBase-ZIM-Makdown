# Command line
Created Samstag 08 Februar 2020

[Source](https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html#id35)
You can pass variables on th command line.

$ ansible-playbook <playbook> --extra-vars "<var 1Y=<value> <var 2>=<value>"
As a file:
$ ansible-playbook <playbook> --extra-vars "@<YAML or JSON file>"


Examples
--------

### Key/value
$ ansible-playbook release.yml --extra-vars "version=1.23.45 other_variable=foo"

### JSON
$ ansible-playbook release.yml --extra-vars '{"version":"1.23.45","other_variable":"foo"}'
$ ansible-playbook arcade.yml --extra-vars '{"pacman":"mrs","ghosts":["inky","pinky","clyde","sue"]}'

