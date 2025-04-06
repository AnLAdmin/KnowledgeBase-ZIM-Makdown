# Create ZFS pool
Created Freitag 29 November 2024

``$ incus storage create <pool_name> zfs [configuration_options...]``

### Documentation
Driver description for [ZFS:](https://linuxcontainers.org/incus/docs/main/reference/storage_zfs/)

* [Storage pool configuration](https://linuxcontainers.org/incus/docs/main/reference/storage_zfs/#storage-pool-configuration)
* [Storage volume configuration](https://linuxcontainers.org/incus/docs/main/reference/storage_zfs/#storage-volume-configuration)
* [Storage bucket configuration](https://linuxcontainers.org/incus/docs/main/reference/storage_zfs/#storage-bucket-configuration)


### Examples
#### Create a loop-backed pool named pool1 (the ZFS zpool will also be called pool1):
$ ``incus storage create pool1 zfs``

#### Create a loop-backed pool named pool2 with the ZFS zpool name my-tank:
``$ incus storage create pool2 zfs zfs.pool_name=my-tank``

#### Use the existing ZFS zpool my-tank for pool3:
``$ incus storage create pool3 zfs source=my-tank``

#### Use the existing ZFS dataset my-tank/slice for pool4:
``$ incus storage create pool4 zfs source=my-tank/slice``

#### Use the existing ZFS dataset my-tank/zvol for pool5 and configure it to use ZFS block mode:
``$ incus storage create pool5 zfs source=my-tank/zvol volume.zfs.block_mode=yes``

#### Create a pool named pool6 on /dev/sdX (the ZFS zpool will also be called pool6):
``$ incus storage create pool6 zfs source=/dev/sdX``

#### Create a pool named pool7 on /dev/sdX with the ZFS zpool name my-tank:
``$ incus storage create pool7 zfs source=/dev/sdX zfs.pool_name=my-tank``

