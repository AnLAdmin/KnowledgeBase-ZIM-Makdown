# Networks
Created Dienstag 07 Januar 2020

[Homepage](https://docs.docker.com/network/)

![](./Networks/pasted_image.png)

Bridge
------
Default is to attach to bridge docker0. Docker0 is not recommended for production. Create a user-defined bridge.
![](./Networks/pasted_image001001.png)

Host
----
Directly attached to the host network. 

Overlay
-------
![](./Networks/pasted_image002.png)

macvlan
-------
![](./Networks/pasted_image001.png)

None
----
Attached to no network. Used in conjunction with a custom network driver.
Is not available to swarm services.

