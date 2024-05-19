# Django
Created Dienstag 31 Dezember 2019


1. Install
2. Create **tests** directory in app directory as package (includes).
3. Create configuration file **pytest.ini** in project directory with at least following content:

[pytest]
DJANGO_SETTINGS_MODULE = ITshelfs.settings
addopts = --cov --cov-report=html

3. Create test\conftest.py for fixtures.
4. Add the following to .coveragerc:

[run]
omit =
*/tests/*
*/migrations/*
*manage.py
*admin.py
*wsgi.py

5. Add the following to VCS ignore file (.hgignore, .gitignore):
	1. htmlcov/*
	2. .coverage


