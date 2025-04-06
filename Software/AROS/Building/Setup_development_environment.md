# Setup development environment
Created Mittwoch 02 April 2025

Based on [manual](https://arosnews.github.io/how-to-cross-compile-aros-hosted-wsl/).

This documentation is to build AROS v11 core-x86_64 and 
Installation
------------
``# apt install git gcc g++ make gawk bison flex bzip2 netpbm autoconf automake libx11-dev libxext-dev libc6-dev liblzo2-dev libxxf86vm-dev libpng-dev gcc-multilib libsdl1.2-dev byacc python3-mako libxcursor-dev cmake genisoimage dh-make yasm curl``

Prepare project
---------------
In /mnt/c/Users/progy/WSL as progy:
``$ mkdir aros``
``$ cd aros``
``$ mkdir scripts``
``$ mkdir arosbuilds``
``$ cd arosbuilds``
``$ git clone`` [``https://github.com/deadwood2/AROS.git``](https://github.com/deadwood2/AROS.git) ``AROS``
IGNORED by me: ``$ cp ./AROS/scripts/rebuild.sh .``

First, build the cross-compiler by running:
``$ ./AROS/scripts/rebuild.sh``

Choose **1) toolchain-core-x86_64**.

Linux-hosted x86_64
-------------------
Proceed with setting up [Linux hosted x86 64 bit build](./Setup_development_environment/Linux-hosted-x86-64.md).

PC native x86_64
----------------
Proceed with setting up [PC native x86 64](./Setup_development_environment/PC-x86-64.md).

Contrib
-------
Get contrib git repository:
``$ git clone`` [``https://github.com/deadwood2/contrib.git``](https://github.com/deadwood2/contrib.git) ``./AROS/contrib``
Build contrib:
``$ cd ~/development/aros/arosbuilds/core-linux-x86_64-d``
``$ make -j4 contrib``
-j4:	run in 4 threads -> Without in one

Test compile

