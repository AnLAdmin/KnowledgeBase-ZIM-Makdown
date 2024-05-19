# Disable Disk Space Monitoring for Loop Devices
Created Samstag 10 Februar 2024

[Src](https://wiki.zimbra.com/wiki/Disable_Disk_Space_Monitoring_for_Loop_Devices)

Problem
-------
1st Scenario: Ubuntu VMs on AWS and Oracle Cloud are generating 100% disk space utilization alert continuously.
2nd Scenario: Exclude a specific volume from disk monitoring.

Sample 'df -Th' output:

zimbra@mail:~$ df -Th
Filesystem     Type      Size  Used Avail Use% Mounted on
udev           devtmpfs  7.9G     0  7.9G   0% /dev
tmpfs          tmpfs     1.6G  162M  1.5G  11% /run
/dev/sda1      ext4       97G  9.7G   88G  10% /
tmpfs          tmpfs     7.9G     0  7.9G   0% /dev/shm
tmpfs          tmpfs     5.0M     0  5.0M   0% /run/lock
tmpfs          tmpfs     7.9G     0  7.9G   0% /sys/fs/cgroup
/dev/sda15     vfat      105M  3.6M  101M   4% /boot/efi
/dev/loop6     squashfs   25M   25M     0 100% /snap/oracle-cloud-agent/8
/dev/loop1     squashfs   55M   55M     0 100% /snap/core18/1880
/dev/loop2     squashfs   42M   42M     0 100% /snap/oracle-cloud-agent/9
tmpfs          tmpfs     1.6G     0  1.6G   0% /run/user/1000
/dev/loop5     squashfs   56M   56M     0 100% /snap/core18/1885
/dev/loop0     squashfs   97M   97M     0 100% /snap/core/9804
/dev/loop4     squashfs   98M   98M     0 100% /snap/core/9993
zimbra@mail:~$

Solution
--------
### Solution 1: Exclude in Localconfig key "zmstat_df_excludes"

Exclude all loop devices from the monitoring.

# su - zimbra (or my zce script)
zimbra$ zmlocalconfig -e zmstat_df_excludes='/dev/loop0:/dev/loop1:/dev/loop2:/dev/loop3:/dev/loop4:/dev/loop5:/dev/loop6'
zimbra$ zmstatctl restart 

Note: There was a bug in old ZCS versions where changing 'zmstat_df_excludes' values does not take effect until logrotate happens.
<https://bugzilla.zimbra.com/show_bug.cgi?id=79148>
### Solution 2: Exclude directly in "zmstat-df" executable file

Run sed command as ROOT user.
# sed -i.bak 's/\/bin\/df -k/\/bin\/df -k -x squashfs -x tmpfs/g' /opt/zimbra/libexec/zmstat-df

Now restart the stats service:
# su - zimbra 
zimbra$ zmstatctl restart 

