# Logs and switch users in multiuser targets

## Changing user with **su**
```sh
# change to user 'user'
su user
```
## bash profile, history, logout, bashrc files
```sh
# bash profile is a customization scrip for login shell, it execute when you login in a shell
~/.bash_profile

# bash logout execute when you logout from bash
~/.bash_logout

# bash history contains all command typed in this shell
~/.bash_history

# bashrc is loaded any time that we log into a user shell
~/.bashrc
```

## change user with login shell
```sh
# to force to use login shell in root user
su - [user]
su -l [user]
su --login [user]
```

## Global profile customisation script
```sh
# global profile, execute for all users
/etc/profile

# profile daemons
/etc/profile.d/

```
