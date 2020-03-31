# Managing Repositories

```sh
# repo configuration files
/etc/yum.repos.d

# see enabled repo list
yum repolist

# see all repolist
yum repolist all

# add repos
yum-config-manager --add-repo=[URL]

# disable repo
yum-config-manager --disable [repo_id]

# enable repo
yum-config-manager --enable [repo_id]
# 
```
