# Samba dataset
Created Freitag 08 November 2024

Setting Up ZFS with Samba.
When setting up Samba with ZFS, the process typically involves:

Creating ZFS Datasets or ZFS Volumes:
You’ll want to create ZFS datasets or volumes to store the files that will be shared over the network using Samba. For instance:
``# zfs create tank/share``

Setting Samba Permissions:
Ensure that the ZFS dataset or volume has appropriate file system permissions set, and that those permissions align with your Samba configuration. For example:
``# chown nobody:nogroup /tank/share``
``# chmod 755 /tank/share``

Configuring Samba:
You will need to configure Samba by editing the smb.conf file (usually located at /etc/samba/smb.conf) to define the share that points to the ZFS dataset or volume. An example configuration could look like this:
```ini
[ShareName]
path = /tank/share
browseable = yes
writable = yes
guest ok = no
```

Here are some tips for optimization
-----------------------------------
ZFS Record Size: For file systems like SMB (which typically works with larger files like videos or documents), you might want to tune the ZFS record size to match the file types. By default, ZFS uses a 128KB record size, but increasing it might help with performance if your files are larger.

Example:
``# zfs set recordsize=1M tank/share``

Samba's aio (Asynchronous I/O): If you're serving large files and want to improve performance, enable asynchronous I/O in Samba for better throughput.

ZFS Compression: Enable compression on the ZFS dataset where you store your SMB shares. For text-heavy files or files that compress well (e.g., log files, databases), this can significantly reduce disk usage and network bandwidth.

Example:
``# zfs set compression=lz4 tank/share``

Samba's Caching: Tweak Samba’s min receivefile size and socket options to increase performance over the network, especially for large file transfers.

ZFS Snapshots for Backup: Take regular ZFS snapshots of the dataset being shared by Samba to provide backup points and quick recovery options (Previous Versions).

