# Create BTRFS pool
Created Freitag 29 November 2024

``$ incus storage create <pool_name> btrfs [configuration_options...]``

### Documentation
Driver description for [BTRFS](https://linuxcontainers.org/incus/docs/main/reference/storage_btrfs/)[:](https://linuxcontainers.org/incus/docs/main/reference/storage_zfs/)

* [Storage pool configuration](https://linuxcontainers.org/incus/docs/main/reference/storage_btrfs/#storage-pool-configuration)
* [Storage volume configuration](https://linuxcontainers.org/incus/docs/main/reference/storage_btrfs/#storage-volume-configuration)
* [Storage bucket configuration](https://linuxcontainers.org/incus/docs/main/reference/storage_btrfs/#storage-bucket-configuration)


### Examples
#### Create a loop-backed pool named pool1:
``$ incus storage create pool1 btrfs``

#### Use the existing Btrfs file system at /some/path for pool2:
``$ incus storage create pool2 btrfs source=/some/path``

#### Create a pool named pool3 on /dev/sdX:
``$ incus storage create pool3 btrfs source=/dev/sdX``

