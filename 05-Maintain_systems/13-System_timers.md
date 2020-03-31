# Configure a System to Use Time Services

```sh
# information about time
timedatectl

# disable ntp
timedatectl set-ntp false

# list timezones
timedatectl list-timezones

# select timezone
tzselect

# set timezone
timedatectl set-timezone America/Mexico_city

# set current time
timedatectl set-time 12:00:00

# chronyd is a daemon for synchronisation of the system clock
# see status
systemctl status chronyd

# see chrony sources
chronyc sources -v

# see more information about time syncronization
chronyc tracking

# see chrony config file
nano /etc/chrony.conf

# restart chrony to see changes if you change pool of server
systemctl restart chronyd
```


