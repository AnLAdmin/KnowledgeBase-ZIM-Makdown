# Set timezone
Created Sonntag 07 Juli 2024

By systemd
----------
List available timezones:
$ ``timedatectl list-timezones``

Set timezone:
# timedatectl set-timezone <Timezone>
E.g. Set timezone to Europe/Zurich:
``# timedatectl set-timezone`` ``Europe/Zurich``

Write timezone string (e.g. Europe/Zurich) to /etc/timezone if the file exists.
echo "<timezone>" > /etc/timezone
E.g.
echo "Europe/Zurich" > /etc/timezone

By symlink
----------
Find zonedata in **/usr/share/zoneinfo**. The symlink **/etc/localtime** shows the crrent setting.

Set timezone by symlinking a timezone file in the directory/subdirectory above:
``# ln -s /usr/share/zoneinfo/<Name or path to tz file> /etc/localtime``

E.g. Set timezone to Europe/Zurich:
``# ln -s /usr/share/zoneinfo/Europe/Zurich /etc/localtime``

Write timezone string (e.g. Europe/Zurich) to /etc/timezone.
echo "<timezone>" > /etc/timezone
E.g.
echo "Europe/Zurich" > /etc/timezone

