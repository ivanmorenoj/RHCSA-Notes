# Configuring a Local Repository: Configure the GPG Key

```sh
# add repository rhel 7
yum-config-manager --add-repo http://dl.fedoraproject.org/pub/epel/7/x86_64

# copy link of GPG key in https://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-7
# go to rpm-gpg
cd /etc/pki/rpm-gpg/

# download gpg key
wget https://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-7

# copy full path of gpg key
# /etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7

# go to yum.repos.d and edit fedora yum repo
# add the next lines
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7
# save and exit
```
