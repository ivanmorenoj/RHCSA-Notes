# List, Create and Delete Partitions on MBR and GPT Disks

## fdisk command

```sh
# see disk partition
fdisk /dev/sdX

# add new partition with 'n' command
#   specify partition number
#   specify first sector, usually leave as is
#   specify last sector +size{K,M,G}
# change the partition type with 't'
#   select partition
#   specify code of partition type (list with 'l')
# white changes an exit with 'w'
# press 'd' to delete partition, first you need to chosee a partition


# create xfs filesystem
mkfs -t xfs /dev/sdXX

# see mounted partitions
df -h

# see available block storage devices tht are attached
blkid

# mount device
mount /dev/sdXX /mnt/mountpoint

# mount from uuid
mount -U [uuid] /mnt/mountpoint

# umount device
umount /mnt/mountpoint

# run partprobe to reload partition information
partprobe
```

## gdisk
Is pretty much the same as fdisk

## GPT allow to create up to 128 primary partition
