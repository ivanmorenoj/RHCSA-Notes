# Configure Key-Based Authentication for SSH

```sh
# generate ssh keys
ssh-keygen

# keys are stored in /home/user/.ssh/

# copy pub key to remote host
ssh-copy-id -i /path/to/public/key user@remotehost

# start ssh agent
ssh-agent bash

# set password for key
ssh-add /path/to/public/key
```