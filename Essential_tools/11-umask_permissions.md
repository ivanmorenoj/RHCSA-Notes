# List, set and change standard UGO/RWX Permissions: unmask

On Linux and other Unix-like operating systems, new files are created with a default set of permissions. Specifically, a new file's permissions may be restricted in a specific way by applying a permissions "mask" called the umask. The umask command is used to set this mask, or to show you its current value.
|umask digit|default file|default directory|
|:---------:|:----------:|:---------------:|
|     0     |      rw    |      rwx        |
|     1     |      rw    |      rw         |
|     2     |      r     |      rx         |
|     3     |      r     |      r          |
|     4     |      w     |      wx         |
|     5     |      w     |      w          |
|     6     |      x     |      x          |
|     7     |      nd    |      nd         |

## umask command
```sh
# return the current umask
umask

# return the current mask in representation mode
umask -S

# set all permissions
umask 000

# set u=rwx permissions
umask 077

# set u=rwx, g=rx and o=x
umask 026
```