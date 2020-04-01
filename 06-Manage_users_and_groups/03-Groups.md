# Create, Delete, and Modify Local Groups and Group Memberships

```sh
# goup file
/etc/group

# get groups of specific user
getent group user

# create a group
groupadd grpname

# change primary group
usermd -g grpname user

# add suplementary group to user
usermod -aG grpname user

# change group
newgrp grpaname -

# change group name
groupmod -n newname oldname

# change group id
groupmod -g 1010 oldname

# delete group
groupdel grpname 
```