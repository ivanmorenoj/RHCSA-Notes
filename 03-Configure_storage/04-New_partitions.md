# Add New Partitions and Logical Volumes and Swap to a System Non-Destructively

## Add swap space
```sh
# se current memory/swap
free -h

# create lvm partition for swap
pvcreate /dev/sdXX
vgcreate vgName /dev/sdXX
lvcreare -n swap -L 2G vgName

# create swap signature
mkswap /dev/vgName/swap

# activate swap 
swapon /dev/vgName/swap

# desactivate swap
swapoff /dev/vgName/swap

# add swap to /etc/fstab file
/dev/vgName/swap swap swap 0,0

# mount swap from fstab
swapon -a

# see swap status
swapon -s 
```








