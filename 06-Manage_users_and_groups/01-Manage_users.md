# Create, Delete, and Modify Local User Accounts

```sh
# see id of specific user
id

# root user have id=0
# system users id=1-200
# System users that use system processes but don't own files on the system id=201-999
# 

# /etc/passwd have all content about users

# see groups of user
groups user

# default options for useradd
/etc/login.defs
/etc/defaults/useradd

# create a user
useradd user

# don't create home directory
useradd -M user

# set password
passwd user

# modify user account
usermod --help

# lock user
usermod -L user

# unlock user
usermod -U user

# change user id
usermod -u 1010 user

# add user to group
usermod -G wheel user

# delete user
userdel user

# delete user and home directory
userdel -r user
```
