#  List and Identify SELinux Files and Process Contexts

```sh
# see context
ls -Z
# output
# system_u:object_r:admin_home_t:s0 file
#   ^User   ^Role      ^Type

# install httpd server to see the context
yum install httpd

# start httpd
systemctl start httpd

# see the context of /var
ls -lZ /var

# list all of the available contexts on our system and files they're associated with
semanage fcontext -l

# Example of SELinux works
cd /home/user
echo "Test Page" > index.html

mv index.html /var/www/html

# reload pagen in index to check
curl -k localhost/index.html

# see file context
ls -lZ /var/www/html

cd /var/www/index.html

# grant all global privilleges
chmod 777 index.html

# reload the page
curl -k localhost/index.html

# see proccess with context
ps auxZ | grep httpd

# retore context
restorecon index.html

# reload the page
curl -k localhost/index.html

# reelabel all on reboot
touch /.autorelabel
```