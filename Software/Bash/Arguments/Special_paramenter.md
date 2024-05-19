# Special paramenter
Created Montag 15 Oktober 2018

-- (double dash)
----------------
More precisely, a double dash (--) is used in bash built-in commands and many other commands to signify the end of command options, after which only positional parameters are accepted.

Example use: lets say you want to grep a file for the string **-v**. Normally **-v** will be considered the option to reverse the matching meaning (only show lines that do not match), but with -- you can grep for string -v like this:
```sh
grep -- -v file
```



