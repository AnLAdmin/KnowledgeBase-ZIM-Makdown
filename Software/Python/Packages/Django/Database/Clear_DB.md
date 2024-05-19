# Clear DB
Created Freitag 08 November 2019

Without deleting db file
------------------------
Deletes all data from the database.
$ manage flush
You have requested a flush of the database.
This will IRREVERSIBLY DESTROY all data currently in the 'C:\\Users\\progy\\Development\\Projects\\ITshelfs_Django\\DBs/db.sqlite3' database,
and return each table to an empty state.
Are you sure you want to do this?

Type 'yes' to continue, or 'no' to cancel:**yes**


With deleting db file
---------------------
Usefull with (a lot) code changes. Because with code changes it will create new migrations.

Delete database file. -> Do this in the filesystem not in pyCharm. -> Less likely to trigger a VCS update.
Delete migrations folder of all apps. -> Do this in the filesystem not in pyCharm. -> Less likely to trigger a VCS update.

