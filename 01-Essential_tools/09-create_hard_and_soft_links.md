# Create hard and soft links

## Linux have 2 types of links: symbolic and hard

## crate link
```sh
# a symbolic link refers to path, if source path change the symbolic link will be broken
# a symbolik link have rwx permission for everyone, because this is just a symilink linking to another
# so these permission do not matter instead the source permissions on our tarjet file is what the system reads when openinig the link  
# create symbolic link
ln -s [source] [tarjet]

# hard link
# a hard link links into inode directly on the filesystem
# the permissions are the same at the source file
# hard links are linked directly to the inode source on the hard drive
# if the source of target files is removed, the created link still exist
# and the data is available on the inode untill all links to that node 
# are no longer available or no longer exist
# All hard links linking to the same file will have the same date time
# as well as permissions
# create hard link
ln [source] [tarjet]


```