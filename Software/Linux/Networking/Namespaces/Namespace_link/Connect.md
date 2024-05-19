# Connect
Created Freitag 07 Februar 2020

Link network namespaces together through their links (interfaces). Also called a pipe.

With this you create 2 connected links:
# ip link add <link name 1 for namespace 1> type veth peer name <link name 2 for namespace 2>
Attach those 2 interfaces to their respective namespaces:
# ip link set <link name 1> netns <namespace 1>
# ip link set <link name 2> netns <namespace 2>

To make them usefull [add IP addresses](./Add_IP_addresses.md) and activate them.

