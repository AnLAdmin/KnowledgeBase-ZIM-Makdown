# Create user
Created Dienstag 13 April 2021

A **user** in PostgreSQL is called a **role**.

PostgreSQL client
-----------------

### User with LOGIN privileges set
$ createuser -P -U <SQL superuser> <Database username> 

SQL
---

### User with LOGIN privileges set
<SQL DB>=# CREATE ROLE <Database username> PASSWORD <Password> LOGIN;

### User without any privileges set
<SQL DB>=# CREATE ROLE <Database username> PASSWORD <Password>;

