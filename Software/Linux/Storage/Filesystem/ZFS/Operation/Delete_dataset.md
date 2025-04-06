# Delete dataset
Created Sonntag 03 November 2024

# zfs destroy <Pool name>/<Dataset name>
-r	Also delete children if any exist
-f	Force unmount
### Example
Delet a dataset without children.
# zfs destroy mypool/dataset1

