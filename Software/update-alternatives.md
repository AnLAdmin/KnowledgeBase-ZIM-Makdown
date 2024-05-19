# update-alternatives
Created Mittwoch 27 März 2024

[man](https://manpages.ubuntu.com/manpages/jammy/en/man1/update-alternatives.1.html)

With update-alternatives we can run different programs under a generic name. We call these programs alternatives. A well-known example is editor, which can refer to vim, nano, or joe.

The command uses symbolic links to keep track of alternatives. Then, update-alternatives accepts commands to manage alternatives without going through the underlying links in /etc/alternatives/.

