# Access remote system using ssh

## Usage
```sh
ssh user@remoteHost
```

## SSH config file
```sh
nano /etc/ssh/sshd_config
```

## SSH service
```sh
# init, stop, enable, disable and see the status with systemctl 
systemctl status,start,stop,enable,disable sshd

# Logs in reverse mode 
journalctl -u sshd -r 
```

## Execute remote command 
```sh
ssh user@remoteHost ls
```

## Copy files through ssh with scp
```sh
# copy file from local to remote over ssh  
scp file user@remoteHost:~/

#copy file from remote to local
scp user@remoteHost:~/file ~/
```

## ftp through ssh 
```sh
# init ftp session over ssh, it means that is an encrypted connection  
sftp user@remoteHost

# it works with regular file commands
sftp> ls,cp,mv,mkdir, etc

# download files
sftp> get file

# upload files
sftp> put localfile
```
