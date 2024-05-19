# Stop
Created Dienstag 07 Januar 2020

$ docker stop <container name/id ...>
This "only" shutdowns a container **without** removing it. A stopped container can only be started again. [Run](./Run.md) does not work.
-> With [ps](./List_running_containers.md) one can get the name(s) or id.

Example
-------

### with ID
$ docker stop ad0b34d4da5f

### with name
$ docker stop eloquent_goodall

