# File format
Created Sonntag 23 Februar 2020

File extension
--------------
.deb

File format
-----------
[ar:	archive format](https://en.wikipedia.org/wiki/Ar_%28Unix%29)

### Tool
[ar](../../ar.md)

Content
-------
debian-binary:		Version of the deb file format,"2.0\n"
control.tar.gz:		Metadata about the packagecontrol, md5sums, (pre|post)(rm|inst), triggers, shlibs, . . .
data.tar.gz:			Data files of the package


