# Clone
Created Montag 15 August 2022

to target with same size
------------------------
Ensure that source and target partition/disk **is unmounted** and will not be automounted.
Use [partclone](../../../../Partclone.md).btrfs:
# partclone.btrfs -b -s /dev/<Source> -o /dev/<Target>

Use btrfstune -u to change UUID after copy and before mounting.
Data loss warning: Do NOT try to (auto)mount either original or copy until the UUID has changed

to target with **different** size
---------------------------------
The steps to "clone" /source to /target where source and target have different disk size. 

Get a list of subvolumes ordered by ogen: 
# btrfs subvolume list -qu --sort ogen /<Source>
Sorting is probably enough to guarantee that snapshots or subvolumes which depend on previous ones are handled first. This is important for dealing with Copy-on-Write, because we need to have the base volumes transferred first.

Make all source subvolumes read-only using:
# btrfs property set -ts /<Source>/<Some volume> ro true

**ATTENTION Direcory or file no-cow attributes get lost. **

Now, for each subvolume from the list above, starting at the top, do the following:

If the volume does not have a parent UUID (displayed as -) or the parent UUID does not exist anymore in the list, run: 
# btrfs send /<Source>/<Some volume> | btrfs receive /<Target>/<mountpoint>

If the volume does have a parent UUID which still exists, we should have transferred it already because of --sort ogen and we can use that as a base to avoid data duplication. Hence, find the parent UUID's path in the list and run: 
# btrfs send -p /<Source>/<Parent>/<Subvolume>/ -c /<Source>/<Parent>/<Subvolume>/ /<Source>/<Some volume>/ | btrfs receive /<Target>/<mountpoint>/ 
(btrfs would probably guess the -p argument automatically, but I prefer to be explicit).

After running one of the above commands make the target and source read-write again: 
# btrfs property set -ts /<Source>/<Some volume> ro false; btrfs property set -ts /<Target>/<Some volume> ro false. 
This step can be skipped if the source has been previously read-only.
([Src](https://superuser.com/questions/607363/how-to-copy-a-btrfs-filesystem))

