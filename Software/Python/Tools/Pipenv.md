# Pipenv
Created Mittwoch 23 Oktober 2019

Description
-----------
[Homepage](https://github.com/pypa/pipenv)
Pipenv is a tool that aims to bring the best of all packaging worlds (bundler, composer, npm, cargo, yarn, etc.) to the Python world. Windows is a first--class citizen, in our world. (Source [PyPI](https://pypi.org/))

Installation
------------
# pip install pipenv

Create env
----------
$ cd <Project directory>
$ pipenv install
$ pipenv shell

Activate env
------------
$ pipenv shell

Deactivate env
--------------
$ exit

Install packages
----------------
$ pipenv install <package name>

Install dev tools
-----------------
$ pipenv install <package name> --dev

Uninstall packages
------------------
$ pipenv uninstall <package name>
All:
$ pipenv uninstall --all
only all dev tools:
$ pipenv uninstall --all-dev

Lock installed SW versions
--------------------------
Something similar to *pip freeze*.
$ pipenv lock

Fresh install locked SW
-----------------------
Normally run on another/clean system. Ignores the pipfile. Uses the lock file.
$ pipenv install --ignore-pipfile

