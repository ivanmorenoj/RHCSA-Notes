# Install and Update Software Packages from Red Hat Network, RPM REPO

```sh
# download rpm package
yumdownloader nano

# install from rpm
rpm -ivh nano-2.9.8-1.el8.x86_64.rpm

# list all packages
rpm -qa

# list specific packages
rpm -qa nano

# list files of specific package
rpm -ql nano

# documentation
rpm -qd nano

# remove package
rpm -e nano

# use localinstall
yum localinstall nano-2.9.8-1.el8.x86_64.rpm
```


