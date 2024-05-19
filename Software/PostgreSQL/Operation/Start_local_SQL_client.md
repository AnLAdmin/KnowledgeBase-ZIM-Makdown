# Start local SQL client
Created Samstag 03 April 2021

Host
----
$ psql [-h <hostname>] [-U <SQL user>]

### Examples
Opens psql with current Linux user (as SQL user with same name) on localhost:
$ psql
Opens psql as as SQL user **postgres** (Default user) on localhost
$ psql  -U postgres

Podman
------
Open PostgreSQL client in container as SQL user **postgres**:
# podman exec -it <Container name> psql [-h <hostname>] -U postgres
E.g: podman exec -it postgresql psql -U postgres

