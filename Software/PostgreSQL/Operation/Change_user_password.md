# Change user password
Created Freitag 09 April 2021

A user in PostgreSQL is called a role.

PSQL
----
<SQL DB>=# \password <User/role name>

SQL
---
<SQL DB>=# ALTER ROLE <User/role name> WITH PASSWORD '<Password>';

### Examples
Change user **postgres** password to **This is @ secure p$$word!**.
<SQL DB>=# ALTER ROLE postgres WITH PASSWORD 'This is @ secure p$$word!';

