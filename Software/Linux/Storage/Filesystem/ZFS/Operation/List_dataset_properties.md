# List dataset properties
Created Sonntag 03 November 2024

List all datasets properies
---------------------------
``# zfs get all``

List all datasets properies sorted
----------------------------------
``# zfs get all | sort``

List all properties of a dataset
--------------------------------
``# zfs get all <Dataset name>``

Getting the current value for a specific property
-------------------------------------------------
``# zfs get <Property name> <Dataset name>``

Setting a property value
------------------------
``# zfs get <Property name>=<Property value> <Dataset name>``
### Example
``# zfs set compression=gzip-1 mypool/mydataset``

