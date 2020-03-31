# Configure Networking and Hostname Resolution Statically or Dynamically: Troubles

## Network commands
```sh
# show ip address
ip addr show

# show ip address of specific interface
ip addr show eth0

# show statics information
ip -s -h link show eth0

# ping to specific ip address
ping -c5 google.com

# follow hops to ip adrress
tracepath google.com
traceroute google.com

# see listening ports and stablish connections
netstat
ss

# see all tcp sockets
ss -at

# see open ports
ss -tan
```

