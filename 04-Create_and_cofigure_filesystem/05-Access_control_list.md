# Create and Manage Access Control Lists (ACLs)

## xfs ext4 support natively ACLs

```sh
# get ACL from file
getfacl file

# set access control list on specific directory
setfacl -m u:username:rw file
# setfacl uses the user id, so if this id change you need to change again the ACL

# set acl permission for only read
setfacl -m m::r file

# mask all permissions
setfacl -m m::- file

# acl for group
setfacl -m g:grpname:rw file

# set default ACL for specific user
sefacl -d -m u:username:rw directory

# set acl for directory
setfacl -m:username:rw directory

# remove default permissions
setfacl --remove-default directory

# remove user permissions
setfacl -x u:username directory

# remove user on default dir
setfacl -x d:u:username directory

# set multiple permissions
setfacl -m g:grpname:rwX,u:username:rw directory

# set acl recursively
setfacl -R -m g:grpname:rwX,u:username:rw directory

# copy acl from file
getfacl file1 | setfacl --set-file=- file2
```

