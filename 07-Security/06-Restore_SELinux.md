# Restore Default File Contexts

```sh
# example using httpd
# modify root directory to /content
nano /etc/httpd/conf/httpd.conf

# create ditectory
mkdir /content

# restart service
systemctl restart httpd

# set apache user an group
chown apache:apache -R /content

# create a basic page
echo "Test Page" > /content/index.html

# see selinux content
cd /content
ls -lZ

# test the page
curl -k localhost/index.html

# change selinux to permissive
setenforce 0

# test the page
curl -k localhost/index.html

# change selinux to enforce
setenforce 1

# get the rigth context for httpd
semanage fcontext -l | grep /var/www
# find /var/www(/.*)? and see the context
# Context:  system_u:object_r:httpd_sys_content_t:s0

# set the right context to /content
semanage fcontext -a -t httpd_sys_content_t '/content(/.*?)'

# see context
ls -lZ

# restore context
restorecon -Rv /content

# see context
ls -lZ

# test the page
curl -k localhost/index.html

# remove one context
# first list
semanage fcontext -l | grep /content
# output:
#   /content(/.*?)  all files   system_u:object_r:httpd_sys_content_t:s0

# remove context
semanage fcontext -d '/content(/.*?)'

# search for context in /content
semanage fcontext -l | grep /content

# restore context
restorecon -Rv /content

# test the page
curl -k localhost/index.html
```