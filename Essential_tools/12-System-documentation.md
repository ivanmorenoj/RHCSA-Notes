# Locate, Read and Use System Documentation with man, info and /usr/share/doc

## man pages
man pages have multiples sections
1. Executable programs or shell commands
2. System calls (functions provided by the kernel)
3. Library calls (functions within program libraries)
4. Special files (usually found in /dev)
5. File formats and conventions, e.g. /etc/passwd
6. Games
7. Miscellaneous  (including  macro packages and conventions, e.g. man(7), groff(7)
8. System administration commands (usually only for root)
9. Kernel routines [Non standard]

## apropos command
apropos command is used to search the manual page names and descriptions

```sh
# search manual pages of passwd command
apropos passwd 

# if retuns nothing, you need to index man pages with
mandb

# consult man page in section 5 of passwd
man 5 passwd
```

## info command
info is gnu information utility
```sh
# get information of info
info info

# info pages are locate in
/usr/share/info

# how to navigate
press 'H' to get info tips

# apropos in info
info --apropos=tee
```

## If a programm doesn't have man or info pages, use --help or -h

## Also you can browse documentation in /usr/share/doc/

## locate command
locate is used to search documentation, executables, etc 
```sh
# search for passwd
locate passwd

# update locate db
updatedb
```
## which command
The 'which' program shows the full path of (shell) commands
```sh
# search for passwd executable
wich passwd
```

## whatis command
whatis command is used to locate the binary, source, and manual page files for a command
```sh
# search for passwd
whatis passwd
```

# whereis command
whereis - locate the binary, source, and manual page files for a command
```sh
# search for passwd
whereis passwd
```



