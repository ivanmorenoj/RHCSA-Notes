# Update the Kernel Package Appropriately to Ensure a Bootable System

```sh
# see kernel version
uname -r

# list kernel
yum list kernel

# download kernel
yumdownloader kernel

# install linux-firmware
yum install linux-firmware

# install kernel from rpm
rpm -ivh kernel-new-version.rpm
```
