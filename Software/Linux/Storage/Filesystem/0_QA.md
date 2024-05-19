# 0 QA
Created Samstag 06 Juni 2020

How does updating running application binaries during an upgrade work?
----------------------------------------------------------------------
Linux (and other UNIXes) draws a distinction between the name of a file (the link), the file itself (often identified with the inode), and open handles to the file. When you go to delete a file, you call the unlink() call - this erases the link to the file (you could also use rename() to overwrite it with a different inode). However, if open handles to the file (or other links - files can have multiple hardlinks) remain, the inode remains, and so does the file content, until all links and handles go away.

So running programs using the library or whatever keep a handle to the old version (often implicitly through a memory mapping), so it stays on disk. It just doesn't have a filename anymore, and will be cleaned up when all programs using it shut down (or on the next reboot, during the filesystem check or journal replay).

Further, note that programs expecting the 'old library' will do just fine with newer versions of the library. Linux libraries are assigned a filename ('soname') that reflects the version of the ABI (Application Binary Interface) offered by the library. For example, the C library on my system is libc.so.6. Any program compiled against an older version of libc, but still a version of libc implementing the version 6 ABI, will work fine with it. Really old programs will look for a libc.so.5 or libc.so.4 or something instead; in this case, you'd need to keep the old version around as well - but since the filename is different, this isn't a problem.


