# Enable for editor
Created Dienstag 16 März 2021

Enable password hash secret
---------------------------
See [here.](./Define_credentialSecret.md)

Admin
-----

### Enable admin password
Uncomment **adminAuth** setting in **settings.js**:
```js
    adminAuth: {
        type: "credentials",
        users: [{
            username: "admin",
            password: "fv3rb5tbrvs4v5v4v3c4cvtg44454tbrgbtes",
            permissions: "*"
        }]
    },

```


### Create password

#### Host install
Generate a new password:
# node-red admin hash-pw
Copy & paste printed hash in the **password** key in settings.js.

#### Docker/Podman
# <Container engine cli> exec -it <Container name> npx node-red admin hash-pw
password: <Enter your passwort her>
Copy & paste printed hash in the **password** key in **settings.js**.

### Restart service
# systemctl restart container-<Container name>.service

User
----
Add additional item(s) to the array users:
```js
    adminAuth: {
        type: "credentials",
        users: [{
            username: "admin",
            password: "<Enter a password hash here>",
            permissions: "<Set a permission>"
        }]
    },
```


### Set permissions
Choose one of the permissions listed bellow:
   *:		full access
   read:	read-only access

Set it in the key **permissions**.

### Finish change
Repeat the steps as with admin starting with **Create password**.

