# Adjust Process Priority and Kill Processes - Part 2

## start a process and send to background
```sh
# & is used to send program to background
(while true: do echo -n "Program" >> ~/output.log; sleep 1; done) &

# see current subprocess in terminal
jobs

# send SIGSTOP signal to job 1
kill -SIGSTOP %1

# send SIGCONT signal to job 1
kill -SIGCONT %1
```

## ps command examples
```sh
# list all sshd 
ps aux | grep sshd

# see process with user-defined format
ps axo pid,comm,nice

# form more examples
man ps
```
