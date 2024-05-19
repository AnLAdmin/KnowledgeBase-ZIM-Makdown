# Configuration
Created Dienstag 10 November 2020

[Orig](https://wiki.ubuntuusers.de/Incron/)
[Orig2](https://www.linux.com/topic/desktop/how-use-incron-monitor-important-files-and-folders/)

Edit incrontab
--------------
# incron [-u <user>] -e

### Incrontab format
```ini
<Path to directory or file> <Event(options) mask> <Path to command> <Parameters>
```


#### Events
Events are separated by coma.
IN_ACCESS		File was accessed (read)
IN_ATTRIB		Metadata changed (permissions, timestamps, extended attributes, etc.)
IN_CLOSE_WRITE		File opened for writing was closed
IN_CLOSE_NOWRITE	File not opened for writing was closed
IN_CLOSE		Opened file/directory was closed
IN_CREATE		File/directory created in watched directory
IN_DELETE		File/directory deleted from watched directory
IN_DELETE_SELF		Watched file/directory was itself deleted
IN_MODIFY		File was modified
IN_MOVE_SELF		Watched file/directory was itself moved
IN_MOVED_FROM		File moved out of watched directory
IN_MOVED_TO		File moved into watched directory
IN_MOVE			file/directory was moved
IN_OPEN			File was opened
IN_ALL_EVENTS		Any event

#### Event options
IN_DONT_FOLLOW	Don't follow symbolic link
IN_ONESHOT	Only watch for one event
IN_ONLYDIR	Only watch if a directory
IN_NO_LOOP	Wait with event watching until command exited

#### Parameter wildcards
$$	Prints a dollar sign
$@	Add the watched filesystem path
$#	Add the event-related file name
$%	Add the event flags (textually)
$&	Add the  event flags (numerically)

#### Examples
Sends a report via a script with path which triggered the event.
```ini
/var/application/error IN_CREATE /var/application/scripts/send_error.sh $@/$#
```

