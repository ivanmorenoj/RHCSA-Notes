# Create, Mount, Unmount and Use VFAT, EXT4 and XFS File Systems

## Create a partition
```sh
# partitioning disk an create a primary partition
fdisk /dev/sdX

# format to vfat
mkfs.vfat /dev/sdXX

# mount filesystem
mount /dev/sdXX /mnt/vfat

# see active mount points
df -h

# edit fstab to make change persistent
nano /etc/fstab
# example of mount for vfat filesystem 
/dev/sdXX /mnt/vfat vfat defaults 1 2

# force create filesystem
mkfs.xfs -f /dev/sdXX
```

## Repartitioning the same disk
```sh
# first umount
umount /mnt/vfat

# delete partition
fdisk /dev/sdX
# press 'd' to delete
# press 'n' to create a new partition an leave defaults

# format to ext4
mkfs.ext4 /dev/sdXX

# mount filesystem
mount /dev/sdXX /mnt/ext4

# edit fstab to make change persistent
nano /etc/fstab
# example of mount for vfat filesystem 
/dev/sdXX /mnt/ext4 ext4 defaults 1 2
```

## Check filesystem and repair any issue
```sh
# for vfat and ext filesystems exixts fsck command

# check vfat filesystem
fsck.vfat /dev/sdXX

# check ext4 filesystem
# first you need to umount
umount /mnt/ext4

# for ext filesystems you don't need to specify the filesystem in fsck command
fsck /dev/sdXX
```

## See details about filesystem
```sh
# see information about filesystem
dumpe2fs /dev/sdXX

# see uuid
blkid

# set label
tune2fs -L label_name /dev/sdXX
```

## xfs troubleshooting
```sh
# see info about xfs filesystem
xfs_info /dev/sdXX

# set label
xfs_admin -L label_name /dev/sdXX

# repair xfs filesystem
xfs_repair /de/sdXX 
```

