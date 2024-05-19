# **kwargs
Created Dienstag 21 April 2020

Placeholder for an unknown number of additional **keyworded** arguments or an unpacked dictionary to the function.
```python
def greet_me(**kwargs):
    for key, value in kwargs.items():
        print("{0} = {1}".format(key, value))

>>> greet_me(name="yasoob")
name = yasoob
```


Unpack Dictionary List
----------------------
Transfer (unpack) dictionary argument values to the function.
```python
>>> def parrot(voltage, state='a stiff', action='voom'):
...     print("-- This parrot wouldn't", action, end=' ')
...     print("if you put", voltage, "volts through it.", end=' ')
...     print("E's", state, "!")
...
>>> d = {"voltage": "four million", "state": "bleedin' demised", "action": "VOOM"}
>>> parrot(**d)
-- This parrot wouldn't VOOM if you put four million volts through it. E's bleedin' demised !
>>> parrot(**{"voltage": "four million", "state": "bleedin' demised", "action": "VOOM"})
-- This parrot wouldn't VOOM if you put four million volts through it. E's bleedin' demised !
```

([Src](https://docs.python.org/3/tutorial/controlflow.html#unpacking-argument-lists))

