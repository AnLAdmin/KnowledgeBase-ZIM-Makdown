# Ubuntu
Created Mittwoch 18 Dezember 2019

18.04
-----

### With repository
based on [Docker Engine Community](https://docs.docker.com/install/linux/docker-ce/ubuntu/) manual.

Update the apt package index:
$ sudo apt-get update
Install packages to allow apt to use a repository over HTTPS: 
$ sudo apt-get install apt-transport-https ca-certificates gnupg-agent software-properties-common [curl]

Add Docker’s official GPG key: 
$ sudo wget -qO - <https://download.docker.com/linux/ubuntu/gpg>  | sudo apt-key add -
**Optionally** wirth curl:
$ sudo curl -fsSL <https://download.docker.com/linux/ubuntu/gpg> | sudo apt-key add -
Verify key **9DB3 5822 9FC7 DE34 814A E2D8 8D81 823C 0FCF CD77**.
$ sudo apt-key fingerprint 0FCFCD77
    
pub   rsa4096 2017-02-22 [SCEA]
  9DB3 5822 9FC7 DE34 814A E2D8 8D81 823C 0FCF CD77
uid           [ unknown] Docker Release (CE deb) <[docker@docker.com](mailto:docker@docker.com)>
sub   rsa4096 2017-02-22 [S]

Setup stable repository for x86_64 / amd64:
$ sudo add-apt-repository "deb [arch=amd64] <https://download.docker.com/linux/ubuntu> $(lsb_release -cs) stable"
$ sudo apt-get update
Install the latest veresion:
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
Verify that Docker Engine - Community is installed correctly by running the hello-world image.
$ sudo docker run hello-world

OPTIONAL: Install [docker-compose](./Ubuntu/docker-compose.md).

### Enable non-privileged user
Create the docker group.
$ sudo groupadd docker
Add your user to the docker group.
$ sudo usermod -aG docker $USER
Logout/-in or activate the changes to the group:
$ newgrp -



