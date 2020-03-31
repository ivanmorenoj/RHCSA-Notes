# Install Red Hat Enterprise Linux Systems as Virtual Guests

## Install operating system with GUI
1. Select iso image
2. Select Memory and CPU
3. Select HDD
4. Set name
5. Start, select hard drive, timezone, etc
6. Set root and user passwords
7. Wait until finish and reboot
8. Access as root and bring up networl with NetworkManager

```sh
# see connections
nmcli con show

# bring up 
nmcli con up ens3

# check internet connection
ping google.com

# check ip address
ip a show ens3

# auto connect on boot
nmcli con mod "ens3" connection.autoconnect yes
```
