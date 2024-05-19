# Deactivate root
Created Mittwoch 25 September 2019
@Linux @Ubuntu

Lock the root user:
```sh
sudo passwd -l root
```


#### Explaination
Lock the password of the named account. This option disables a password by changing it to a value which matches no possible encrypted value (it adds a ´!´ at the beginning of the password).

