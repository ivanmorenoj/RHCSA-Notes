# Install Red Hat Enterprise Linux Automatically Using Kickstart

PXE Server contain all information about new installation
```sh
# anakonta-ks.cfg is the configuration file

# install GUI configuration
yum install system-config-kickstart

# launch GUI an modify parameters
system-config-kickstart

# find documentation for pykickstart
rpm -qd pykickstart

# open kickstart-docs.txt to see configurations

# to test kickstart
# put ks.cfg in a pxe server
# install from PXE server in KVM
```