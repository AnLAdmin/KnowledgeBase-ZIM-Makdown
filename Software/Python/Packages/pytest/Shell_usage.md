# Shell usage
Created Mittwoch 13 November 2019

Lists some usefull command line invocation.

Run all test
------------
$ pytest
or 
**$ python -m pytest**
-> The second variant is more [python compatible](https://docs.pytest.org/en/latest/pythonpath.html#pytest-vs-python-m-pytest).

Run all test with verbose output
--------------------------------
$ pytest -v

Run a specific test file
------------------------
$ pytest <test file>.py

Run tests parallel
------------------
The package **pytest-xdist **has to be installed.
$ pytest -n 3
-> Runs 3 workers in parallel.

Run test which contain string in name
-------------------------------------
$ pytest -k <string>
E.g. <string> = great, runs tests test_*great*(), test_*great*er(), test_*great*er_equal(), ...

Run test with outputs
---------------------
Shows stdoutput on screen. E.g. print ('Text')
$ pytest -s

Show fixtures
-------------
Shows builtin and custom fixtures.
$ pytest --fixtures

Execute marked tests
--------------------
$ pytest -m <(part of) marker name>


