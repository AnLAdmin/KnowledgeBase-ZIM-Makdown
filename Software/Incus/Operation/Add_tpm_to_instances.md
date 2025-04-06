# Add tpm to instances
Created Samstag 07 Dezember 2024

If an OS needs TPM it is possible to add a [virtual TPM](https://linuxcontainers.org/incus/docs/main/reference/devices_tpm/).
$ ``incus config device add <Instance name> <Device name> tpm [path=<Device path in instance>]``

### Example
$ ``incus config device add win11vm vtpm tpm path=/dev/tpm0``

