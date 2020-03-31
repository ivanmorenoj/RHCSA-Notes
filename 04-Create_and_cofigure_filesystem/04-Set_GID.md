# Create and Configure Set-GID Directories for Collaboration

## set permissions
```sh
# set g-id to directory
chmod g+s dir

# add group grp
groupadd grp

# change group owner
chown :grp dir

# create a file to see file permissions
touch dir/file
```


