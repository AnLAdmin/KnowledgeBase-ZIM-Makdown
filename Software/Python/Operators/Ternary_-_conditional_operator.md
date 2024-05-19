# Ternary - conditional operator
Created Montag 13 Januar 2020

Javascript / C
--------------
```js
expression ? positive value : negative value
x>y ? x : y
```

If the expression is true x is returned if false y is returned.

Python
------
In Python there are 4 ways to do this.

### Shortened if-else
```python
x if x>y else y
```


### Tuple
```python
(y,x)[x>y]
```


### Dictionary
```python
{True: x, False: y} [x > y]
```


### Lambda
```python
(lambda:y,lambda:x)[x>y]()
```

