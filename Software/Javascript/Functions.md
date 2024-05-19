# Functions
Created Montag 25 November 2019

Regular binding -> Function value
---------------------------------
This works like a variable square. One can handle it like a normal variable binding. To call this function the binding has to be **defined before the call**, like a variable.
```js
const square = function(x) {
  return x * x;
};
```


Declaration
-----------
Works like a function definition in other programming languages. -> Needs no semicolon at the end. The function can be **declared anywhere** in the code.
```js
function square(x) {
  return x * x;
}
```


Arrow functions
---------------
Work like regular bindings but make it possible to write smaller functions. Some sort of lambda functions in other languages, but not identical.
```js
const power = (base, exponent) => {
  let result = 1;
  for (let count = 0; count < exponent; count++) {
    result *= base;
  }
  return result;
};
```

With one parameter:
```js
const square1 = (x) => { return x * x; };
const square2 = x => x * x;
```

Without parameters:
```js
const horn = () => {
  console.log("Toot");
};
```

