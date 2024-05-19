# Duplicate database
Created Dienstag 17 August 2021

This describes the cloning of an existing database.

PostgreSQL client
-----------------
Dump source database:
$ pg_dump -U <SQL superuser> -d <Database to export> -f <Exports file path>
Create new database to import previously exported data:
$ createdb -U <SQL superuser> -O <Database owner> <Target database>
Import previously exported data:
$ psql -U <SQL superuser> -d <Target database> -f <Export file path>

SQL
---
CREATE DATABASE [Database to create]
WITH TEMPLATE [Database to copy]
OWNER [Database username];

### E.g.
CREATE DATABASE nextcloud-test WITH TEMPLATE nextcloud OWNER postgres;

