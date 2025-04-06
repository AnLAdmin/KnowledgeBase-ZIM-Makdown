# List pool properties
Created Sonntag 03 November 2024

List all pools properies
------------------------
``# zpool get all``

List all pools properies sorted
-------------------------------
``# zpool get all | sort``

List all properties of a pools
------------------------------
``# zpool get all <Pool name>``

Getting the current value for a specific property
-------------------------------------------------
``# zpool get <Property name> <Pool name>``
### Example
``# zfs get compression mypool``

