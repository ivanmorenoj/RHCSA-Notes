# Using LVM

LVM is a logical volume manager for the Linux kernel; it manages disk drives and similar mass-storage devices.

## LVM building blocks
Logical Volume Management utilizes the kernel's device-mapper feature to provide a system of partitions independent of underlying disk layout. With LVM you abstract your storage and have "virtual partitions", making extending/shrinking easier (subject to potential filesystem limitations).

Virtual partitions allow addition and removal without worry of whether you have enough contiguous space on a particular disk, getting caught up fdisking a disk in use (and wondering whether the kernel is using the old or new partition table), or, having to move other partitions out of the way.

Basic building blocks of LVM:

## Physical volume (PV)
Unix block device node, usable for storage by LVM. Examples: a hard disk, an MBR or GPT partition, a loopback file, a device mapper device (e.g. dm-crypt). It hosts an LVM header.
## Volume group (VG)
Group of PVs that serves as a container for LVs. PEs are allocated from a VG for a LV.
## Logical volume (LV)
"Virtual/logical partition" that resides in a VG and is composed of PEs. LVs are Unix block devices analogous to physical partitions, e.g. they can be directly formatted with a file system.
## Physical extent (PE)
The smallest contiguous extent (default 4 MiB) in the PV that can be assigned to a LV. Think of PEs as parts of PVs that can be allocated to any LV.

### Example:

### Physical disks
```
  Disk1 (/dev/sda):
     _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _
    |Partition1 50 GiB (Physical volume) |Partition2 80 GiB (Physical volume)     |
    |/dev/sda1                           |/dev/sda2                               |
    |_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ |_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ |

  Disk2 (/dev/sdb):
     _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _
    |Partition1 120 GiB (Physical volume)                 |
    |/dev/sdb1                                            |
    |_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _|
```
### LVM logical volumes
```
  Volume Group1 (/dev/MyVolGroup/ = /dev/sda1 + /dev/sda2 + /dev/sdb1):
     _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _
    |Logical volume1 15 GiB  |Logical volume2 35 GiB      |Logical volume3 200 GiB              |
    |/dev/MyVolGroup/rootvol |/dev/MyVolGroup/homevol     |/dev/MyVolGroup/mediavol             |
    |_ _ _ _ _ _ _ _ _ _ _ _ |_ _ _ _ _ _ _ _ _ _ _ _ _ _ |_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _|
```
## Advantages
LVM gives you more flexibility than just using normal hard drive partitions:

- Use any number of disks as one big disk.
- Have logical volumes stretched over several disks.
- Create small logical volumes and resize them "dynamically" as they get filled up.
- Resize logical volumes regardless of their order on disk. It does not depend on the position of the LV within VG, there is no need to ensure surrounding available space.
- Resize/create/delete logical and physical volumes online. File systems on them still need to be resized, but some (such as ext4) support online resizing.
- Online/live migration of LV being used by services to different disks without having to restart services.
- Snapshots allow you to backup a frozen copy of the file system, while keeping service downtime to a minimum.
- Support for various device-mapper targets, including transparent filesystem encryption and caching of frequently used data. This allows creating a system with (one or more) physical disks - (encrypted with LUKS) and LVM on top to allow for easy resizing and management of separate volumes (e.g. for /, /home, /backup, etc.) without the hassle of entering a key multiple times on boot.
- Disadvantages
- Additional steps in setting up the system, more complicated. Requires (multiple) daemons to constantly run.
- If dual-booting, note that Windows does not support LVM; you will be unable to access any LVM partitions from Windows.
- If your physical volumes are not on a RAID-1, RAID-5 or RAID-6 losing one disk can lose one or more logical volumes if you span (or extend) your logical volumes across multiple non-redundant disks.

## Examples

## Create lvm partition
```sh
gdisk /dev/sdX
# press 'n' and create a new partition
# change type to 8e00 - Linux LVM
# make this for all physical volumes

# define physical volumes for LVM
pvcreate /dev/sdX1 /dev/sdY1

# see available volumes
pvdisplay

# create volume group
vgcreate vgName /dev/sdX1 /dev/sdY1

# display volume group
vgdisplay

# creale logical volume
lvcreate -n lvName -L 10G vgName

# display logical volume name
lvdisplay

# create filesystem
mkfs -t xfs /dev/vgName/lvName

# mount
mount /dev/vgName/lvName /mnt/mountPoint

# remove logical volume
lvremove /dev/vgName/lvName

# remove volume group
vgremove vgName

# remove physical volume
pvremove /dev/sdX1 /dev/sdY1
```

