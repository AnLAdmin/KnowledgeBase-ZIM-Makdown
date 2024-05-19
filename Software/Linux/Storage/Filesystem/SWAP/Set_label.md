# Set label
Created Sonntag 28 April 2024

First stop the swap you want to (re)label:
# swapoff /dev/<Partition name>
(Re)label swap:
# swaplabel -L <Label name> /dev/<Partition name>
Reactivate swap:
# swapon /dev/<Partition name>

