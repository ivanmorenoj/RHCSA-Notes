# Boot, Reboot and Shutdown a System

## systemd is a software suite that provides an array of system components for Linux operating systems.

## Reboot system
```sh
# reboot with systemd
systemctl reboot
```

## Shutdown system
```sh
# use shutdown to reboot in 5 minutes 
shutdown -r +5

# shutdown inmmediately
shutdown now

# stop all services with systemctl
systemctl halt

# power off with systemctl
systemctl poweroff
```


