# Configuration
Created Montag 03 Februar 2020

Contains some initial configuration.

Security for Windows drives
---------------------------
Files and directories on mounted windows drives get rwxrwxrwx by default. To change that add the following to **/etc/wsl.conf**:
```ini
[automount]
optins = "metadata,umask=22,fmask=11"
```

-> This works only for newly created files/directories.

