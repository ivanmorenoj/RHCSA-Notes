# Archive, Compress, Unpack and Uncompress files using tar, star, gzip and bzip2

## tar itself is not compressing, it create archive
```sh
# create an archive
tar -cvf archive.tar [FILE]...

# see files inside an archive.tar
tar -tf archive.tar

# once is in tar format it can be compressed
gzip archive.tar    # output archive.tar.gz

# compress and archive in one command
tar -cvfz archive.tar.gz [FILE]...

# uncompress archive step by step
gzip -d archive.tar.gz
tar -xvf archive.tar

# uncompress in one command
tar -xvfz archive.tar.gz

# see the difference between files in tar and current directory
tar -dvf archive.tar.gz 

# gzip command
gzip -l file # see the compression ratio
gzip -d file # uncompress
```

## start utility
```sh
# create archive
star -c -f=archive.tar [FILE]...

# extract archive, it doesn't override alredy existing files
star -x -f=archive.tar

# extract one file of archive
star -x -f=archive.tar onefile
```

