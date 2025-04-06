# Configuration
Created Samstag 16 November 2024

### Initiate Incus
([Src](https://linuxcontainers.org/incus/docs/main/howto/initialize/))

#### Initialize Incus interactive
OPTIONALLY [install vSwitch](../vSwitch/Installation/Ubuntu/24.04.md) as alternative to Linux bridges if you plan to go to **multiple server deployment**.
OPTIONALLY initiate [without default bridge](./Configuration/No_default_bridge.md).

``$ incus admin init``
Would you like to use clustering? (yes/no) [default=no]:
Do you want to configure a new storage pool? (yes/no) [default=yes]:
Name of the new storage pool [default=default]:
Name of the storage backend to use (btrfs, dir, lvm) [default=btrfs]:
Would you like to create a new btrfs subvolume under /var/lib/incus? (yes/no) [default=yes]: 
Create a new BTRFS pool? (yes/no) [default=yes]: 
Would you like to create a new local network bridge? (yes/no) [default=yes]:
What should the new bridge be called? [default=incusbr0]: 
What IPv4 address should be used? (CIDR subnet notation, “auto” or “none”) [default=auto]:
What IPv6 address should be used? (CIDR subnet notation, “auto” or “none”) [default=auto]:
Would you like the server to be available over the network? (yes/no) [default=no]:
Would you like stale cached images to be updated automatically? (yes/no) [default=yes]:
Would you like a YAML "init" preseed to be printed? (yes/no) [default=no]: **yes**

Backup YAML output.

#### Security - Local daemon access
To give local full access to a non-root user [add the user](../Linux/Security/Group/Operation/Add_user.md) to the group **incus-admin**.
There is another group **incus** to give per-user project access to Incus.
##### Container security
([Src](https://linuxcontainers.org/incus/docs/main/explanation/security/#container-security))

* ☐ Incus: [Harden security](https://linuxcontainers.org/incus/docs/main/explanation/security/#about-security) !! @Todo



* ☐ Incus: [Production settings](https://linuxcontainers.org/incus/docs/main/reference/server_settings/) !!! @Todo
* ☐ Incus: [Performance tuning](https://linuxcontainers.org/incus/docs/main/explanation/performance_tuning/) !!! @Todo
* ☐ Incus: Backup !!! @Todo
* ☐ Incus: Add Docker Hub as repository for application container !! @Todo


