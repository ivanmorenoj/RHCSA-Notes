# Mount and Unmount CIFS and NFS Network File Systems

## Preparing the sneario
```sh
# install samba-cliente ntfs cifs
yum -y install samba-client cifs-utils nfs-utils
```

## Acces to samba share
```sh
# access to samba server
smbclient -L [IP_ADDRESS_SERVER]

# mount sambashare
mount -t cifs -o username=username,password=pass //[IP_ADDRESS]/sambashare /mnt/sambashare

# see active mounts
df -h

# mount ntfs share
mount -t ntfs [IP_ADDRES]:/sambashare /mnt/ntfsshare

# make mount persistent
# edit /etc/fstab
# for cifs
//[IP_ADDRESS]/sambashare /mnt/sambashare cifs username=username,password=passs 0 0
# for ntfs
[IP_ADDRESS]:/ntfsshare /mnt/ntfsshare ntfs defaults 0 0

#test fstab file
mount -a
```



