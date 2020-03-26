# Input/Output Redirection

## Redirec standard output [1] (override the file if it exist)
```sh
cat /etc/issue > somefile.txt
```

## Append contend 
```sh
cat /etc/issue >> somefile.txt
```

## Redirect standard error [2] (redirect error to file)
```sh
bad_command 2> badcommand.txt
```

## Redirect both stdout and stderr to file 
```sh
command &> badcommand.txt
```

## Redirect stderr[2] to stdout[1] 
```sh
command 2>&1 | grep "command"
```

## Pipes (redirect stdout of one command to stdin of another command)
```sh
ls /etc | grep system 
```

## Append stderr [2] to file
```sh
ls -fy >> logfile.log 2>&1 
```


