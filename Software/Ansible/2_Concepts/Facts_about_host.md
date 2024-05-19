# Facts about host
Created Montag 24 Februar 2020

Get available facts with a play
-------------------------------
```yaml
...
	- debug: var=ansible_facts	# all facts
...
	- debug: var=ansible_distribution	# specific facts
```


Get raw availalbe information
-----------------------------
All facts.
$ ansible -m setup <host pattern>
To get specific facts set a filter
$ ansible web -m setup -a 'filter=ansible_eth*'

Access facts variables
----------------------
```yaml
{{ ansible_fqdn }}
{{ ansible_facts['fqdn'] }}
{{ ansible_facts['devices']['xvda']['model'] }}
{{ ansible_facts.devices.xvda.model}}
```

