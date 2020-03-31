# Configuring a Local Repository

```sh
# mount rhel dvd
mount -o loop rhel-iso.iso /repos/local

# disable rhel repos
# create a local repo
nano /etc/yum.repos.d/local-repo.repo

# write this
[local-repo]
name=Red Hat Linux Local Repo
baseurl=file:///repos/local
enabled=1
gpgcheck=0

# test 
yum search emacs

# install from local repo
yum install emacs
```
