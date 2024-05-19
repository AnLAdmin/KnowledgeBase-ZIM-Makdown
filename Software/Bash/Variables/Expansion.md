# Expansion
Created Sonntag 26 Januar 2020

Simple
------
```sh
echo $VAR
```


In text
-------
```sh
echo file.${VAR_WITH_EXTENSION}
```


Default value
-------------
If the variable is empty the spcified default is used:
```sh
echo file.${VAR:-<default value>}
```

