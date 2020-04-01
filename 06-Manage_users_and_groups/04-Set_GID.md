# Using set-GID On Directories

```sh
# Example of congiguration with GID

mkdir groups

cd groups

mkdir galactica

groupadd galactica

chown :galactica galactica

useradd vipper
passwd vipper

usermod -aG galactica vipper

chmod g+w galactica

# access as vipper user
cd galactica

touch file

ls -l

# as root user
chmod g+s galactica

# as vipper user
cd galactica

touch file2

ls -l

# see diferent files permissions
```