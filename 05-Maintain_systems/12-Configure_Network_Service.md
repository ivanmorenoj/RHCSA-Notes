# Configure Network Services to Start Automatically at Boot

```sh
# see service
systemctl status network

# see units for network
systemctl list-units | grep network.target

# see dependencies for multi-user target
systemctl list-dependencies multi-user.target

# see network script
cat /etc/sysconfig/network-scripts/ifcfg-eth0

# set suto connect from NetworkManager
nmcli con mod "eth0" connection.autoconnect yes
```

