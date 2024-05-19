# Deb
Created Freitag 03 September 2021

Get package
-----------
Get package from githubs release page:
# wget <Link to deb file>
The next to steps are necessary that apt can access the deb file.
# cp <Path to deb file> /tmp/
# chmod 0777 /tmp/<deb file>

Install/Upgrade
---------------
Install micro:
# apt install <Path to deb file>
# rm /tmp/<deb file>

