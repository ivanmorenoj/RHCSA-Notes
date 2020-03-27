# Adjust Process Priority and Kill Processes - Part 1

## ps command
The ps command is used to find an list process runing in the system

```sh
# basic ps usage
ps

# grep specific process
ps | grep ssh

# pgres is similar to ps | grep
pgrep ssh

# list process name
pgrep ssh -l

# list the process own bay specific user
pgrep -u user -l chrome

# process that not own by specific user
pgrep -v -u user -l
```

## pkill command
pkill - look up or signal processes based on name and other attributes
```sh
pkill vim 
```

## signals
```sh
# The basic syntax is as follows:
kill PID
kill -s signalName PID
kill -signalName PID
kill -signalNumber PID
# list all signals
kill -l

# kill pts od ssh session
pkill -t pts/1
pkill -u user sshd
```
## Some basic signals

|Number|Name (short name)|Description|Used for               |
|:----:|:---------------:|:---------:|:----------------------|     
|0     |SIGNULL (NULL)	 |Null	     |Check access to pid     |
|1	   |SIGHUP (HUP)	 |Hangup	 |Terminate; can be trapped|
|2	   |SIGINT (INT)	 |Interrupt	 |Terminate; can be trapped|
|3	   |SIGQUIT (QUIT)	 |Quit	     |Terminate with core dump; can be trapped|
|9	   |SIGKILL (KILL)	 |Kill	     |Forced termination; cannot be trapped|
|15	   |SIGTERM (TERM)	 |Terminate	 |Terminate; can be trapped|
|24	   |SIGSTOP (STOP)	 |Stop	     |Pause the process; cannot be trapped. This is default if signal not provided to kill command.|
|25	   |SIGTSTP (STP)	 |Terminal	 |Stop/pause the process; can be trapped|
|26	   |SIGCONT (CONT)	 |Continue	 |Run a stopped process|

