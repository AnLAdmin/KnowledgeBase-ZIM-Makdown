# Create a vSwitch bridge
Created Samstag 20 Juli 2024

Create an ovs L3 bridge
-----------------------
``incus-admin$ incus network create <name> --type=bridge bridge.driver=openvswitch``

Create an L2 ovs bridge connected to a NIC port
-----------------------------------------------
This is a L2 bridge without own IP address, no NAT/FW and no DHCP server.
``$ incus network create <Network name> --type=bridge bridge.driver=openvswitch bridge.external_interfaces=<NIC port name> ipv4.address=none ipv4.dhcp=false ipv4.firewall=false ipv4.routing=false ipv6.address=none ipv6.dhcp=false ipv6.firewall=false ipv6.routing=false``
### Example
$ ``incus network create incusbrlan0 --type=bridge bridge.driver=openvswitch bridge.external_interfaces=enp1s0f1``

