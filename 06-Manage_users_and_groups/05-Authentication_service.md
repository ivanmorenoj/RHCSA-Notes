# Configure a System to Use an Existing Authentication Service for User and Group

```sh
# install used packages
yum install -y realmd

# discover
realm discover ad.linuxacademy.com

# install required packages
yum install oddjob oddjob-mkhomedir sssd adcli samba-common

# join to domain
realm join ad.linuxacademy.com

# check 
realm discover ad.linuxacademy.com

# uncomment an set to yes Kuberos options
nano /etc/ssh/sshd_config

# restart sshd
systemctl restart sshd

# login
ssh -l test@ad.linuxacademy.com [ip_address]

# use GUI
authconfig-gtk
```