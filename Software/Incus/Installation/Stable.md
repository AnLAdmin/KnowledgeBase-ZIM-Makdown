# Stable
Created Freitag 14 Juni 2024

This installs from a [Zabbly](https://github.com/zabbly/incus) ([zabbly.com](https://zabbly.com/)) repository the stable branch. This branch will get more current upgrades.
**Default installation:** **Single instance, NO cluster, BTRFS subvolume as default storage pool separated as subvolume, default bridge**

Incus daemon/container engine
-----------------------------
### Add repository
Get the public key to verify the repository:
``$ wget -q -O -`` [``https://pkgs.zabbly.com/key.asc``](https://pkgs.zabbly.com/key.asc) ``| gpg --show-keys --fingerprint``
Check if the keys fingerprint is identically to the own on the [page](https://github.com/zabbly/incus#installation).
Store the repository public key locally:
``$ wget -O /etc/apt/keyrings/zabbly.asc`` [``https://pkgs.zabbly.com/key.asc``](https://pkgs.zabbly.com/key.asc)

Add the repository for the stable branch:
``# sh -c 'cat <<EOF > /etc/apt/sources.list.d/zabbly-incus-stable.sources``
``Enabled: yes``
``Types: deb``
``URIs:`` [``https://pkgs.zabbly.com/incus/stable``](https://pkgs.zabbly.com/incus/stable)
``Suites: $(. /etc/os-release && echo ${VERSION_CODENAME})``
``Components: main``
``Architectures: $(dpkg --print-architecture)``
``Signed-By: /etc/apt/keyrings/zabbly.asc``

``EOF``'
``# apt update``

OPTIONALLY: [Install](../../QEmu-KVM/Installation.md) Qemu for VM support.
OPTIONALLY: [Install](./1_Optionals.md) some usefull support tools.

### Install
OPTIONALLY Create separate subvolume **/var/lib/incus** for Incus data if you want to use Snapper (or similar tools).

Install engine:
``# apt install incus``

OPTIONALLY install [web client](./Stable/Clients.md#web-interface).
OPTIONALLY install [Incus client](./Stable/Clients/Ubuntu.md) (without Incus server) and configure [Remote access over TLS](./Stable/Clients.md#remote-access-over-tls).




