# Locate and Interpret System Log Files and Journals

## log directory

```sh
/var/log

# you can use diferents tools to see logs
cat /var/log/messages

tail /var/log/messages

less /var/log/messages

head /var/log/messages
```

## journald for systemd based systems
```sh
# man pages of journald
man systemd-journald

# journald tool
journlactl

# journald by default is volatile
# make persistent un comment
# Storage=auto 
nano /etc/systemd/journald.conf

# see the last 10 lines of journalctl
journalctl -n

# see the last logs and follow
journalctl -f

# see aditional information
journalctl -nx

# see short status os specific service
systemctl status sshd

# see journalctl messages by priority
journalctl -p info

# see journalctl since specific time
journalctl --since yesterday

# filter logs messages by systemd unit
journalctl _SYSTEMD_UNIT=sshd.service
journalctl -u sshd.service

# see information abaout boot process
systemd-analyze

# audir system boot
systemd-analyze blame 
```

