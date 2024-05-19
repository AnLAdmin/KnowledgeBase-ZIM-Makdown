# Create
Created Mittwoch 29 Januar 2020

Local
-----
Assignment
```sh
[set] VAR=<value>
```

e.g: set PATH=/bin
With spaces
```sh
[set] VAR="<value>"
```

e.g. name="Anton User"

Global
------
```sh
export VAR=<value>
```


For one command execution
-------------------------
This will set the variables only for the command called in the same line.
$ VAR1=<value> VAR2=<value> <command> <command args>

Permanently
-----------
Put it in one of the shell startup scripts (e.g. .bashrc).

