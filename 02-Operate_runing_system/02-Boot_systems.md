# Boot Systems into Different Targets Manually

## list unit configuration
```sh
# list availabe unit types
systemctl -t help

# list units filtering by target
systemctl list-units --type=target

# see dependencies of target unit file
systemctl list-dependencies multi-user.target

# get default target
systemctl get-default

# some common targets are
multi-user.target, graphical.target, emergency.target, recue.target

# navigate into targets
systemctl isolate multi-user.target

# set default target
systemctl set-default multi-user.target
```



