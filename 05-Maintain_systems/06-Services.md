# Start and Stop Services and Configure Services to Start Automatically at Boot

```sh
# see status
systemctl status httpd

# start service
systemctl start httpd

# see if is enable
systemctl is-enable httpd

# enable service
systemctl enable httpd

# see if service is dependenci of specific target
systemctl list-dependencies multi-user.target | grep httpd
```

