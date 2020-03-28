# Configure Systems to Mount File Systems at Boot by UUID or Label

## create a label on filesystem

```sh
# create a label on xfs filesystem
xfs_admin -L labelName /dev/sdXX

# create a label with tune2fs for ext4 fs
tune2fs -L labelName /dev/sdXX

# make persistent mount points
# open /etc/fstab
nano /etc/fstab

# see mount options in fstab and mount man pages
man fstab
man mount

# to mount, specify UUID=[UUID] LABEL=[LABEL] or device
# example
UUID=[UUID] / ext4 rw,relatime 1 1
LABEL=[LABEL] /mnt/data xfs rw,relatime 0 2
/dev/sdXX   /mnt/data1 ext4 defaults 0 2

# mount all fstab file
mount -a
```







