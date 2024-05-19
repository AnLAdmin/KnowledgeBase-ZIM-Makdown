# Directory structure
Created Dienstag 26 November 2019

Project
-------
Created with
$ django-admin startproject mysite

mysite/	# This is the project root directory. You can change the name to what ever you like
manage.py
mysite/	# Project python package
__init__.py
settings.py	# Settings/configuration for this Django project
urls.py	# Starting point to your projects url hierarchy
wsgi.py	# Entry point for WSGI server

App
---
Created with:
$ py manage.py startapp polls

<App name>/
__init__.py
admin.py
apps.py
migrations/
__init__.py
models.py
tests.py
urls.py	# Starting point to your apps url hierarchy
views.py

