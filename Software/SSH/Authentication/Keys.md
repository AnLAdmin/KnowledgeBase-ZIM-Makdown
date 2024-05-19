# Keys
Created Montag 27 Januar 2020

Create SSH keypair
------------------
$ ssh-keygen <key type settings> -C "<Friendly description>" -f ~/.ssh/<output file>
key type settings:
-t ed25519 -> PREFFERED: most secure. Create all SSH will use the moste secure variant.
-t ecdsa -b 521
-t rsa -b 4096
output file:
The name has to follow a naming scheme: id_<key type>
See -t option above.

-> Move the keys to a secure location, e.g user network directory.

### Deploy public key

#### Linux
-> To login to copy the public key[s] password authentication has to be enabled in **/etc/ssh/sshd_config**: __Verify this!__
```ini
PasswordAuthentication yes
```

Copy keys:
$ ssh-copy-id [<user>@]<target host>

#### Windows

##### Start ssh-agent service
This has to be done once per client.
# By default the ssh-agent service is disabled. Allow it to be manually started for the next step to work.
# Make sure you're running as an Administrator.
```powershell
Get-Service ssh-agent | Set-Service -StartupType Automatic (delayed)
```

Start the service
```powershell
Start-Service ssh-agent
```

This should return a status of Running
```powershell
Get-Service ssh-agent
```


#### Add public key
Load your key files into ssh-agent on the client:
PS> ssh-add <Path to key>\<Key name>

#### Copy public key to server
Make sure that the .ssh directory exists in your server's user account home folder **<Path to user home directory>/.ssh**.
Use scp to copy the public key file generated previously on your client to the authorized_keys file on your server
PS> scp <Path>\id_ed25519.pub <Username>@<host>/home/<username>/.ssh/authorized_keys

