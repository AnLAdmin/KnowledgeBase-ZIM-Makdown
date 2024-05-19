# Create
Created Dienstag 07 Januar 2020

$ docker network create [--driver <[network type](../Networks.md)>] [-o "com.docker.network.bridge.name"="<bridge name>"] <network name>

--driver:								Defaults to bridge.
-o "com.docker.network.bridge.name":	Sets a custom bridge name (visible with *ip address*).

Examples
--------
Create a network of type bridge.
$ docker network create my-network

