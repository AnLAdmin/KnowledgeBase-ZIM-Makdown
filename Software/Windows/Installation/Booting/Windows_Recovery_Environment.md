# Windows Recovery Environment
Created Samstag 16 April 2022

Partitioning
------------
PS> diskpart
Identify system disk:
DISKPART> lis dis
DISKPART> sel dis <Number of system disk | disk to store WinRE>
Prefered is to store the partition before the boot partition (Easier to expand boot partition). But can be anywhere on a disk.
DISKPART> create par pri size=< >600 MB>
Format and name partition:
DISKPART> format fs=NTFS quick label=Recovery
Set partition type to Recovery:
DISKPART> set id=DE94BBA4-06D1-4D40-A16A-BFD50179D6AC
Mark partition as required (needs OVERRIDE to delete):
DISKPART> gpt attributes=0x8000000000000001

Install WinRE
-------------
([src](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/deploy-windows-re?view=windows-11))
R	Drive to Recovery partition
PS> mkdir <R>:\Recovery\WindowsRE
Mount your installation media and copy **WinRE.wim** and the uninitialized **ReAgent.xml:**
Open ISO:\sources\install.wim with a ZIP tool.
Copy install.wim:\Windows\system32\Recovery\**WinRE.wim **and** ReAgent.xml **to *C:\Windows\System32\Recovery*.
PS> reagentc /enable


