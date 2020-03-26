# Create, delete, copy and move files and directories

## touch command
```sh
# create files
touch {file1, file2, file3}

# also is used to change modification time on file
touch existingfile
```

## create directories
```sh
# create a directory
mkdir {dir1,dir2,dir3}

# create multiple directories in the path
mkdir -p dir1/dir2/dir3
```

## tree command
```sh
# see all directories in tree
tree [parent_directory]
```

# delete directory
```sh
# delete an empty directory
rmdir directory

# delete an non empty directory
rm -rf directory 
```

# mv command
```sh
# move files or directory
mv file destination

# rename file or directory
mv file renamedfile
```

# cp command
```sh
# copy file
cp file destination

# copy directory
cp -r directory destination
```
