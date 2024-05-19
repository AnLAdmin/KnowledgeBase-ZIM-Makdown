# Evaluate storage size
Created Mittwoch 16 Oktober 2019

Total directory size
--------------------
$ du -k <Directory path> | awk '{print $1}'
-k: Size in Kilobyte (1024 byte)

Total size of defined type of files
-----------------------------------
$ du -k -c <Directory path>/*.<extension> | tail -1 | awk '{print $1}'
-k: Size in Kilobyte (1024 byte)
-c: Total size

Total storage size
------------------
$ df -k <path to dev> | tail -1 | awk '{print $4}'

