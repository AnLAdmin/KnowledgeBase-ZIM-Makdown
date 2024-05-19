# Create network
Created Samstag 14 November 2020

[Src](http://docs.podman.io/en/latest/markdown/podman-network-create.1.html)

Variables
---------
Network name:	Name of the network to create
CIDR subnet:	Subnet in CIDR to assign to network

With subnet defined
-------------------
This creates a network with the specified subnet and the lowest IP address as default gateway. DNS is enabled.
# podman network create --subnet <CIDR subnet> <Network name>

E.g.
# podman network create --subnet 10.99.0.0/16 cloud

OPTIONAL Add DNS

