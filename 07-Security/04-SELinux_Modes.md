# Set Enforcing and Permissive Modes for SELinux

```sh
# get the current satate of selinux
getenforce

# set permissive mode
setenforce 0

# set enforce mode
setenforce 1

# see config file
nano /etc/selinux/config
```