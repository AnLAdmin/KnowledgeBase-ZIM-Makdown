# Add device to profile
Created Sonntag 21 Juli 2024

([Src](https://linuxcontainers.org/incus/docs/main/reference/manpages/incus/profile/device/add/#incus-profile-device-add-md))
This adds a instance device configuration to an existing Incus profile.
``$ incus profile device add <Profile name> <Device name> <Device type> <Device option key>=<Device option value> ...``

### Example
Add a device configuration which adds a NIC **eth0** into a instance (container/VM) which is connected to a host bridge **incuslanbr0** to the profile **default**.
``$ incus profile device add default eth0 nic network=incuslanbr0 name=eth0``

