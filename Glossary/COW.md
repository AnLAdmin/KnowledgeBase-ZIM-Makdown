# COW
Created Freitag 10 Januar 2020

= Copy-on-write

In the copy-on-write method, when a change to the original volume occurs (but before the write I/O request is completed), each block to be modified is read and then written to ([VSS](../Software/Windows/Services/Volume_Shadow_Copy.md): the volume's shadow copy storage area (also called its "diff area")) free device blocks.

