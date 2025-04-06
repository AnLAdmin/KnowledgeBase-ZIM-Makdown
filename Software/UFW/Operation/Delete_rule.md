# Delete rule
Created Samstag 23 November 2024

delete <Rule>
Rule	Repeate the exact rule definition command
This allows to delete IPv4 and IPv6 in one go.

### Example
Delete a rules created with
``# ufw deny 80/tcp``
like
``# ufw delete deny 80/tcp``

### with number
[List](./List_rules.md#with-numbers) rules with numbers first. Than delete it with the number
``# ufw delete`` <Rule number>

### Example
Delete rule number 3
``# ufw delete`` 3

