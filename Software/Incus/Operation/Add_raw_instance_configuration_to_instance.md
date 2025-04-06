# Add raw instance configuration to instance
Created Samstag 07 Dezember 2024

([Src](https://linuxcontainers.org/incus/docs/main/reference/instance_options/#raw-instance-configuration-overrides))

Incus allows to add raw Qemu/lxc options (and others) to an instance. For this use the instance option ``raw.qemu`` or ``raw.lxc``.

**Important**
**Setting raw.* keys might break Incus in non-obvious ways. Therefore, you should avoid setting any of these keys.**

[See](https://discuss.linuxcontainers.org/t/support-for-virtio-sound/21610/4) here a way to get to raw device options.

SPICE sound
-----------
Add a spice sound device to the instance through QEMU raw options.
``$ incus config set <Instance name> raw.qemu -- "-device intel-hda -device hda-duplex -audio spice"``
### Example
``$ incus config set win11vm raw.qemu -- "-device intel-hda -device hda-duplex -audio spice"``

