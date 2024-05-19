# Fixtures
Created Mittwoch 13 November 2019

Provides a fixed baseline upon which tests can reliably and repeatedly execute. Works similar like setup/teardown functions.
They can be placed in test files directly or in a corresponding *conftest.py* (prefered).

Example
-------
```python
@pytest.fixture
def input_value():
   input = 39
   return input
```

