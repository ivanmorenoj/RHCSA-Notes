# Configure Systems to Launch Virtual Machines at Boot

## From Command line
```sh
# enable libvirtd
systemctl enable --now libvirtd

# enter in virsh
virsh

# list all vm's
list --all

# configure autostart
autostart vm-name
```