# Adjust Process Priority and Kill Processes - Part 3

## nice and niceness
Nice and nice level dows it allows us to define a priority for specific process

nice is a program found on Unix and Unix-like operating systems such as Linux. It directly maps to a kernel call of the same name. nice is used to invoke a utility or shell script with a particular CPU priority, thus giving the process more or less CPU time than other processes. ***A niceness of -20 is the highest priority and 19 is the lowest priority***. The default niceness for processes is inherited from its parent process and is usually 0

## Examples
```sh
# list process pid, command and niceness
ps axo pid,comm,nice | grep sshd

# start a command with niceness of 0
nice -n 0 sshd

# modify niceness of specific process
renice -n 10 [PID]

# renice process and his childs
renice -n 10 $(pgrep sshd)
```

## Niceness demostration
```sh
# create a 1Gb file
dd if=/dev/zero of=file bs=1M count=1024

# compress nith niceness of 19
nice -n 19 tar -cvf test.tar file
# output:
#   0.09s user 2.31s system 47% cpu 5.065 total

# compress nith niceness of -20
nice -n -20 tar -cvf test.tar file
# Output:
#   0.12s user 2.28s system 49% cpu 4.879 total
```
## Note
Only privileged users have the ability to give they process more favor


