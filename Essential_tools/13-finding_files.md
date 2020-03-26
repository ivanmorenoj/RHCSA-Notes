# Finding Files with Locate and Find

## locate command
locate - find files by name
```sh
# find passwd with locate, command and other types of files
locate passwd
```

## find command
'find' searches the directory tree rooted at each file name FILE by
evaluating the EXPRESSION on each file it finds in the tree.
```sh
# examples

# find file by name
find /path -name namesearch

# find by user owner
find /path -user root

# find in currecnt directory
find . -name user

# find in root directory
find / -name passwd

# find all files that have been modified within the last three days
find / -mtime -3

# see stat of file
stat /path/to/file

# find files own by specific user
# get uid
id username
# find files by uid
find / -uid [uid]

# find only files that own by specific user
find / -user username -type f

# find only files that own by specific user and execuute one command
find / -user username -type f -exec cat {} \;
#                                       ^return path of file
```






