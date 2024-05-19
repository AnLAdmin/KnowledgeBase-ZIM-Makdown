# Markers
Created Mittwoch 13 November 2019

Like tags. One can mark/tag a function. ([Doc](https://docs.pytest.org/en/latest/mark.html))

Example
-------
```python
@pytest.mark.great
def test_greater_equal():
   num = 100
   assert num >= 100
```


Registering marks
-----------------
You can register *custom* marks in your **pytest.ini** file like this:
Everything after **:** is an optional description.
```ini
[pytest]
markers =
    slow: marks tests as slow (deselect with '-m "not slow"')
    serial
```

or with a hook in the corresponding conftest.py:
```python
def pytest_configure(config):
    config.addinivalue_line(
        "markers", "env(name): mark test to run only on named environment"
    )
```

