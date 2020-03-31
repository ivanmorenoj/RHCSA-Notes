# Extend Existing Logical Volumes

## Create lvm volume
```sh
# partitioning disk an change type to LVM 8e
fdisk /dev/sdX

# create a physical volume
pvcreate /dev/sdX1

# create a volume group
vgcreate vgName /dev/sdX1

# create logical volume
lvcreate -n lvName -L 1G vgName

# create filesystem
mkfs -t xfs /dev/vgName/lvName

# mount logical volume
mount /dev/vgName/lvName /mnt/lvolume

# create lvm volume in GPT device
gdisk /dev/sdY

# add new partition to existing volume group
# first create a physical volume
pvcreate /dev/sdY1 

# extend vgName to new disk
vgextend vgName /dev/sdY1

# copy pne physical volume to another
pvmove /dev/sdY1

# remove one physical device
pvreduce vgName /dev/sdX1

# extend logical volume
lvextend -L +4G /dev/vgName/lvName
lvextend -l +50%FREE /dev/vgName/lvName

# resize filesystem
xfs_growfs /mnt/lvolume 
```










