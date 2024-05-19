# 0 Issues
Created Mittwoch 29 Januar 2020


* ☐ Ansible: Cannot handle SSH host authenticity prompts for multiple hosts @Issue

Issue is known but not solved.
**Workaround 1:**
Implement **certificate SSH authentication**. Temporarly use option **--ssh-common-args='-o StrictHostKeyChecking=no' **until it's setup.
**Workaround 2:**
Separatly call the hosts with an ad-hoc commend like ping to register the finger print or implement **certificate SSH authentication**.
**Workaround 3:**
Disable host key checking by host groups.
Add to **/etc/ansible/hosts** [servers_group:vars]:
```ini
[servers_group:vars]
ansible_ssh_common_args='-o StrictHostKeyChecking=no'
```

**Workaround 4:**
Disable host key checking permanently globally, by user or byplaybook.
In env ANSIBLE_HOST_KEY_CHECKING or add to **ansible.cfg**:
```ini
[defaults]
host_key_checking = False
```

