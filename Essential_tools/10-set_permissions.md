# List, set and change standard UGO/RWX Permissions

file owner
- u - user
- g - group
- o - other
- a - all

permissions
- r - read -> 4
- w - write -> 2
- x - execute -> 1

## see the file permission
```sh
ls -l

# output
drwxr-xr-x 2 ivan ivan 4.0K Mar 24 22:05
^ u  g  o  
d means directory, l symilink
           ^ hardlink
  ^user       ^ username owner
     ^group        ^ groupname owner
        ^other          ^ file size
                              ^ modification time 

```
## change user permissions
```sh
# change user permission, add excecute to user
chmod u+x file

# change permissions recursively
chmod g+w -R directory

# set execute permissions only for directory with X (capital)
chmod ug+X -R directory

# set read permission for all (user,group and other)
chmod a+r file

# octo permissions
# 4 -> read
# 2 -> write
# 1 -> execute
#
# example rwx = 7 (4+2+1)
# Octo permission: 755   
#                 ^user
#                  ^group
#                   ^other

# examples
# set user read and write, group read
chmod 640 file # equals chmod u+rw,g+r file
```

## add a group
```sh
# command to add a group
groupadd [groupname]
```

## change owner of file or directory
```sh
chown [OWNER][:[GROUP]] FILE...
```

## add user to group
```sh
usermod -aG grouptoadd user
```

## set primary group for current user
```sh
newgrp group
``` 

## setuid and setgid 
```sh
# uid represent by 's'
# uid means that the file will be execute as perrmissions who owns the file
# it has one more bit
# 4 for user and 2 for group, 6 for both
# example
# set uid to file for user
chmod 4500 file # equals chmod u+rxs file

# sticky bit prevents a user from deleting a file on directories
# if the sticky bit is set it will prevent unauthorized users removing 
# or renaming a directory and a file in the directory unless they own the file
# octo notation
# 1 -> sticky bit  
# example
# set the sticky bit on file
chmod +t file

# example: set read, write and execute for user, group and other, set sticky bit
# and set uid to user and group:
# 1st byte = 1 (sticky bit) + 4 (user uid) + 2 (group uid) = 7
# 2nd byte = 4 (read) + 2 (write) + 1 (execute) = 7  
# 3th byte = 4 (read) + 2 (write) + 1 (execute) = 7  
# 4th byte = 4 (read) + 2 (write) + 1 (execute) = 7
# final octal notation = 7777
# set permissions
chmod 7777 file # equals to chmod a+rwx,u+s,g+s,+t file
```