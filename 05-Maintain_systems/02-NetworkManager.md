# Networking and Hostname Resolution Statically or Dynamically: Network Manager

## NetwokManager
```sh 
# see devices
ls /sys/class/net
nmcli dev status # network manager
nmtui # text based gui

# show all connections
nmcli con show

# show active connections
nmcli con show --active 

# all connections are saved in this directory
/ect/sysconfig/network-scripts

# add new connection, by default takes dhcp
nmcli con add con-name "mycon" autoconnect yes type ethernet ifname eth1

# add new connection with static ip address
nmcli con add con-name "mycon-static" autoconnect yes type ethernet ifname eth1 ip4 [ip_address] gw4 [gateway_ip_address]

# modify network to autoconnect
nmcli con mod "mycon" conne

# bring down connection
nmcli con down "mycon-static"

# delete connection
nmcli con del "mycon" 

# bring up connection
nmcli con up "mycon" connection.autoconnect yes

# see routes
ip route show
```

