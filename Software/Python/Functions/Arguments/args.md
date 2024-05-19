# *args
Created Dienstag 21 April 2020

Placeholder for an unknown number of positional non-keyworded arguments or an unpacked list of values to the function.

```python
def test_var_args(f_arg, *argv):
    print("first normal arg:", f_arg)
    for arg in argv:
        print("another arg through *argv:", arg)

test_var_args('yasoob', 'python', 'eggs', 'test')
```


Unpack Argument List
--------------------
Transfer (unpack) lists values as positional argument values to the function.
```python
>>> list(range(3, 6))            # normal call with separate arguments
[3, 4, 5]
>>> args = [3, 6]
>>> list(range(*args))            # call with arguments unpacked from a list
[3, 4, 5]
>>> list(range(*[3, 6]))
[3, 4, 5]
```

([Src](https://docs.python.org/3/tutorial/controlflow.html#unpacking-argument-lists))

