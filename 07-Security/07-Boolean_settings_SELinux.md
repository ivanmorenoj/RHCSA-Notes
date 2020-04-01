# Use Boolean Settings to Modify System SELinux Settings

```sh
# get all boolean settings
getsebool -a
semanage boolean -l

# install httpd
yum install httpd -y

# change to public html
sed -i 's/disabled/public_html/' /etc/httpd/conf.d/userdir.conf

# restart httpd service
systemctl restart httpd

cd /home

chmod 711 user

cd user

mkdir public_html

echo "Test Page" > public_html/index.html

chown user:user -R public_html
chmod 755 -R public_html

# check page
curl -k localhost/~user

# set selinux to permissive
setenforce 0

# set selinux to enforce
setenforce 1

# see selinux boolean
semanage boolean -l | grep httpd_enable_homedirs
# output:
#   httpd_enable_homedirs          (off  ,  off)  Allow httpd to enable homedirs

# set on to homedirs
setsebool httpd_enable_homedirs on

# check page
curl -k localhost/~user

# set boolean persistent
setsebool -P httpd_enable_homedirs on
```