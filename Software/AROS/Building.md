# Building
Created Mittwoch 17 August 2022

Some pointers
-------------

### ae.amigalife.org - Message from [magorium](https://ae.amigalife.org/index.php?PHPSESSID=b7001b030936090c9f0a2b9db9774a5c&topic=976.msg12679#top)
Quote from: PortablE on August 16, 2022, 10:09:16 PM

I hadn't realised that GCC/etc from the Linux-hosted version of AROS could be run outside of AROS (on Linux itself),

Unfortunately it can't.

Quote

... so it seems I need to look for a pre-compiled version of the Linux-hosted AROS & it's developer tools (if that even exists).

Pre compiled versions of AROS ABIv0 Linux hosted can be found at <https://axrt.org/index.php?tab=download-aros>

And as always has been the case you can use the contrib archive to 'obtain' the development directory which contains the /native/ AROS gcc compiler and tools.

What deadwood wrote is that when you build AROS as described that it automatically builds the AROS cross-compiler for you.

That compiler is used to build AROS itself but can be used outside the AROS build process by providing --sysroot with indicated directory to cross compile for AROS.

Quote

Thanks for the pointer - but I was hoping for a pre-compiled version that would avoid me having to install subversion & the huge number of other dependencies needed to build AROS.  (That may not be a show-stopper, but it will at least greatly delay anything AROS-related that I do, as I don't want to have all that 'junk' installed onto my main Linux system.  Possibly I can use chroot or toolbox to keep it entirely separate, but I have not used either of them yet, and they will probably be more complicated than I hope.)

I have no idea about your setup but in case you do have a development machine that has enough free ram (> 8 GB, Unfortunately I do not have an exact figure) then there is no need for a (permanent) installation.

The build instructions as indicated will build everything outside your current system setup. If your setup is able to accomplish that in ram (ramdisk) then you could zip/tarball the directories that you require/desire and re-use those at your disposal (to avoid having to build the whole AROS tree over and over again). Not an ideal solution but it might perhaps be able to address some of your concerns.

But perhaps deadwood has a quicker/better solution as I am not very familiar with AROS' build system.

