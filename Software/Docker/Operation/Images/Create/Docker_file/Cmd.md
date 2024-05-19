# Cmd
Created Mittwoch 08 Januar 2020

This command will be executed at [startup](../../../Container/Run.md) of the container if no command is specified.
A specified command at startup will override the in Cmd defined default command.

Syntax
------


Use with Entrypoint
-------------------
One can use Cmd as default value for Build:Cmd:Entrypoint.

### Example
Dockaerfile:
Entrypoint: sleep
Cmd: 5
$ docker run <container>
Executes sleep 5.
$ docker run <container> 10
Overrides 5. Runs sleep 10.
$ docker run <container> sleep 25
Overrides Entrypoint and Cmd. Runs sleep 25.

Override default Entrypoint
---------------------------
$ docker --entrypoint <command> run <container>
One will get a command not found error if <command> doesn't exist in the image.


