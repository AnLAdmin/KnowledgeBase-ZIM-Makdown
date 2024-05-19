# Create snapshot manually
Created Sonntag 31 Juli 2022

Single
------
Create a standalone simple snapshot ([Src](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/storage_administration_guide/snapper-creating-snapshot#snapper-creating-single-snapshot)):
#/$ # snapper -c <[Config name](../Glossary/Config_name.md)> create -t single [-d "<Description>"]

Pre/post
--------

### Pre
Creates a pre snapshot ([Src](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/storage_administration_guide/snapper-creating-snapshot#snapper-create-pre)):
#/$ snapper -c <[Config name](../Glossary/Config_name.md)> create -t pre -p [-d "<Description>"]

#### E.g.
# snapper -c home create -t pre -p "<Description>"
Output: 2

### Post
Create a post snapshot that is linked to a previously created pre snapshot ([Src](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/storage_administration_guide/snapper-creating-snapshot#snapper-create-post)): 
#/$ snapper -c <[Config name](../Glossary/Config_name.md)> create -t post --pre-num <Pre snapshot number> [-d "<Description>"]
Pre snapshot number: The number of the previously created pre snapshot.

#### E.g.
Post snapshot is based on the pre snapshot in the [pre example above](#Software:Snapper:Operation:Create snapshot manually#eg):
# snapper -c home create -t post --pre-num 2

### Automatically with a command
Wrap a command in pre and post snapshots.
#/$ snapper -c <[Config name](../Glossary/Config_name.md)> create --command "<Command>" [-d "<Description>"]
Command: Before and after this command is a snapshot created.


