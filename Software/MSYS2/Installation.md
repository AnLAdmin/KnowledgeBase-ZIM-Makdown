# Installation
Created Dienstag 14 Januar 2020

->Installation is done as normal user. Running without permissions to the msys64 directory leads to permission denied errors.
This will installe the core utils e.g. no gcc.

Go to <http://www.msys2.org> (Additional [installation informations](https://github.com/msys2/msys2/wiki/MSYS2-installation))
Download msys2 installer executable. 
Install it to a secure location **C:\Users\<user>\Appdata\Local\Programs\msys64** (for x64 version).
At the end lauch msys
Update msys2 system:
$ pacman -Syu
-> May show a warning like **Terminate MSYS2 without returning to shell and check for updates again.**. Close console and restart with MSYS2 MSYS batch scripts.
Update th rest:
$ pacman -Su

