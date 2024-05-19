# Completion
Created Sonntag 26 Januar 2020

Troubleshoot
------------

### Check if set for command
$ complete | grep <command>
Output: complete -F _minimal <command>
This means a minimal default is set because no spacific completions for the command were found.

### Debugging
Set the _ARC_DEBUG variable in your shell to enable verbose debug output every time argcomplete runs.
$ export _ARC_DEBUG=1

### Remove completion
$ complete -r <command>
As soon as you tabed a first time for completion the <command> specific completions should be set. 
-> The **_minimal**  function is set if no specific completions are available.

