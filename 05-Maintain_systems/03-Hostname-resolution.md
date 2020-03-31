# Network/Hostname Resolution Statically or Dynamically: Hostname Configuration

## DNS resolution
```sh
# local host resolution file
/etc/hosts

# nameserver resolution file
/etc/resolv.conf

# system resolve file
/etc/nsswitch.conf

# see current hostname
hostname

# change hostname via hostnamectl tool
hostnamectl set-hostname mydomain.com

# status of hostname
hostnamectl status

# change dns server via NetworkMAnager
nmcli con modify "System eth0" ipv4.dns 8.8.8.

# get host address
getent hosts google.com
```

