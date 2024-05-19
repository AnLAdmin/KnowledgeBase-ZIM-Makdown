# Define credentialSecret
Created Dienstag 16 März 2021

Uncomment **credentialSecret** setting in settings.js:
```js
...
credentialSecret: "a-secret-key",
...
```


Create a hash with:
# < /dev/urandom tr -dc _A-Z-a-z-0-9 | head -c${1:-32};echo;
and replace "a-secret-key" with it:
```js
...
credentialSecret: "<Enter result here>",
...
```


