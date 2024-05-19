# Roles
Created Sonntag 09 Februar 2020

[Roles](https://galaxy.ansible.com/docs/contributing/creating_role.html)
[Galaxy](https://docs.ansible.com/ansible/latest/galaxy)


With roles you can group together variables, files, tasks and handlers in a defined filesystem hierarchy and load (import/include) them into a play(book).

Filesystem structure
--------------------
.travis.yml
README.md
defaults/
main.yml
files/
handlers/
main.yml
meta/
main.yml
tasks/
main.yml
templates/
tests/
inventory
test.yml
vars/
main.yml

