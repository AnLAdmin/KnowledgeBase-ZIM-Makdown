# docker-compose
Created Samstag 06 Juni 2020

Prerequisites
-------------
Install [Docker](../Ubuntu.md).

Installation
------------
Check current version on [Github](https://github.com/docker/compose/releases) and change **<version>** to the correct release number, than download:
# wget -O /usr/local/bin/docker-compose "<https://github.com/docker/compose/releases/download/>**<version>**/docker-compose-$(uname -s)-$(uname -m)"
Apply executable permissions to the binary:
# chmod +x /usr/local/bin/docker-compose

### Install compose BASH completion
Change **<version>** to the correct release number, than download:
# wget -O /etc/bash_completion.d/docker-compose <https://raw.githubusercontent.com/docker/compose/>**<version>**/contrib/completion/bash/docker-compose
Activate it:
# . /etc/bash_completion.d/docker-compose

