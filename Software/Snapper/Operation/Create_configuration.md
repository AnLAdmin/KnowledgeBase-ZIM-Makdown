# Create configuration
Created Samstag 17 September 2022

Default
-------
Create a new default configuartion for a specific subvolume:
$ snapper -c <Configuration name>[|<Configuration name>, ...] create-config <Subvolume>[|<Subvolume>,...]

Custom based on a template
--------------------------
$ snapper -c <Configuration name>[|<Configuration name>, ...] create-config -t <Configuration template name> <Subvolume>[|<Subvolume>,...]
Configuration template name: one listed in **/etc/snapper/config-templates/**

