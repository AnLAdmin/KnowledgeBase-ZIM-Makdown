# Set repository directory as safe
Created Sonntag 14 Januar 2024

When you want to access a local repository as a user which didn't create the repository you get an error:
fatal: detected dubious ownership in repository at '<Directory path>'
'<Directory path>' is owned by:
'S-1-5-21-2143211195-2031170208-1671232068-1012'
but the current user is:
'S-1-5-21-2100321195-2031170208-1612342068-1035'
To add an exception for this directory, call:

git config --global --add safe.directory '<Directory path>'

### Solution
([Source,](https://git-scm.com/docs/git-config#Documentation/git-config.txt-safedirectory) [Src2](https://weblog.west-wind.com/posts/2023/Jan/05/Fix-that-damn-Git-Unsafe-Repository))
As the user who didn't create the repository execute this command:
$  git config --global --add safe.directory "<Directory>"
E.g.: git config --global --add safe.directory 'C:\data\repository'

