# Create systemd files
Created Samstag 05 Dezember 2020

Variables
---------
Application name:	Name of the container

Create service unit files
-------------------------
First create (podman run / create) the container.
#  podman generate systemd --new --files --name <Application name>
Copy the generated system unit file:
# cp container-<Application name>.service /etc/systemd/system/
[Update](../../Systemd/Operation/Update_systemd_configuration.md) systemd configuration.
Enable service:
# systemctl enable container-<Application name>.service
Start service:
# systemctl start container-<Application name>.service


