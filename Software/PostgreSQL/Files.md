# Files
Created Mittwoch 07 April 2021

[Source](https://www.postgresql.org/docs/13/runtime-config-file-locations.html)

List of specific PostgreSQL files and directories.

/var/lib/postgresql/data	Data directory
postgresql.conf			PostgreSQL global configuration located in the data directory.
postgresql.auto.conf		PostgreSQL global configuration located in the data directory.
  It is editied by the server (e.g. ALTER SYSTEM command).
  It is ready every time postgresql.conf is. This overides settings from postgresql.conf.
[pg_hba.conf](https://www.postgresql.org/docs/13/client-authentication.html)			Specifies the configuration file for host-based authentication. Located in the data directory.
  This parameter can only be set at server start.


