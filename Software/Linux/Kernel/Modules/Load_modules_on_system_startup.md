# Load modules on system startup
Created Freitag 17 Mai 2024

This will load the defined mosules at startup.

Add module to /etc/modules-load.d/<Sensor module name>.conf:
(File scan contain more than one module name separated by newline.)
```sh
# Enter what why
<Sensor module name>
```
Add options if NECESSARY for the module above to /etc/modprobe.d/<Sensor module name>.conf:
```sh
options <Sensor module name> <Key>=<Value> ...
```

