# Configure a Physical Machine to Host Virtual Guests


```sh
# install dependencies
yum install virt-manager qemu-kvm qemu-img
yum install libvirt libvirt-python python-virtinst libvirt-client

# enable libvirt
systemctl enable --now libvirtd

# manage vm's
virsh
```

