# Regular Expressions

## The grep command -> grep, egrep, fgrep - print lines that match patterns
```sh
SYNOPSIS
    grep [OPTION...] PATTERNS [FILE...]
    grep [OPTION...] -e PATTERNS ... [FILE...]
    grep [OPTION...] -f PATTERN_FILE ... [FILE...]

OPTIONS
  -E, --extended-regexp     PATTERNS are extended regular expressions
  -i, --ignore-case         ignore case distinctions in patterns and data
  -v, --invert-match        select non-matching lines
```
### See all lines start by '#' with ^ in front of pattern
```sh
grep '^#' /etc/ssh/sshd_config
```
### See all lines that not start by '#' with ^ in front of pattern
```sh
grep -v '^#' /etc/ssh/sshd_config
```
### Find a pattern 'memery' in dmesg command
```sh
dmesg | grep 'memory'
```

### Find lines that ends with 'world' using $
```sh
grep 'world$' 03-patterns.txt
```
### Find all 'linuxacademy' without case sensitive 
```sh
grep -i 'linuxacademy' 03-patterns.txt
```
### Find all '[Ll]inuxacademy' pattern L or l 
```sh
grep  [Ll]linuxacademy 03-patterns.txt
```
## Extended regular expressions 
```sh
grep -E '(a)+' 03-patterns.txt
grep 'l...x' 03-patterns.txt

grep 'login$' /etc/passwd
```



