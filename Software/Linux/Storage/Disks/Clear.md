# Clear
Created Montag 15 August 2022

This command(s) clears all partition imformation from disk. (Similar to [this](../../../Windows/Storage_Management/Disks/Clear.md) on Windows.)

Method 1
--------
``# blkdiscard <Device> -v [-f]``
-f	force

### E.g.
``# blkdiscard /dev/nvme0n4 -v``

Method 2
--------
``# wipefs -a [-f] <Device>``
-f	force

### E.g.
``# wipefs -a /dev/sda``

