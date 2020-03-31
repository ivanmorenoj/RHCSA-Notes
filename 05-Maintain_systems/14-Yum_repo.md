# Install and Update Software Packages from Red Hat Network, YUM REPO

```sh
# check update
yum check-update

# update all packages
yum update

# update specific package
yum update httpd

# search packages by name
yum search apache

# search all packages and descriptions
yum search all apache

# see information
yum info httpd

# install packages
yum install httpd

# see installed packages
yum list installed

# see specific installed package
yum list installed httpd

# see what package create a file
yum provides /var/www
yum whatprovides /var/www

# remove a package
yum remove httpd

# clean cache
yum clean all
```