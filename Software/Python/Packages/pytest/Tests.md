# Tests
Created Mittwoch 13 November 2019

How to write test and customize them.

Basic
-----
Test
```python
def test_<name>()
	<some support code, e.g. var definition, framework initilizations (-> use fixtures), ...>
	assert <test>
```

Example:
```python
def test_equality():
   assert 10 == 11


def test_sqrt():
   num = 25
   assert math.sqrt(num) == 5
```


Parameterizing Tests
--------------------
Parameterizing of a test is done to run the test against multiple sets of inputs.
Example:
```python
import pytest

@pytest.mark.parametrize("num, output",[(1,11),(2,22),(3,35),(4,44)])
def test_multiplication_11(num, output):
   assert 11*num == output
```

-> Runs 4 sets of values.

