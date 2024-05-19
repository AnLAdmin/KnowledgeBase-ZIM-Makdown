# Migrations
Created Dienstag 26 November 2019

Migrations are how Django stores changes to your models (and thus your database schema).  This are Python files.
Migrations are tracked in the table **django_migrations** in the database.

Location
--------
<Project>\<App>\migrations

Apply to database
-----------------
Call [makemigrations](./manage.py.md).

