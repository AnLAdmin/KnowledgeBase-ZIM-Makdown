# Create DB
Created Freitag 08 November 2019

With existing migrations
------------------------
This asumes that the necessary <App> migrations exists but no or empty database. Create django and contrib tables. Applies the migrations in the <App>/migrations folder to the database.
$ manage(.py) migrate
Create [superuser](../Project/Setup/Create_superuser.md).

No migrations
-------------
Only the models in <App>/models.py exist but no or empty database.

Initialize database:
$ manage migrate
Create migrations for <App:
$ manage makemigrations <App>
Apply migrations to database:
$ manage migrate <App> -> Repeat for the other apps
Create [superuser](../Project/Setup/Create_superuser.md).

