# Diagnose and Address Routine SELinux Policy Violations

```sh
# install tool to see troubleshoot
yum install setroubleshoot-server

# turn off homedirs bool
setsebool httpd_enable_homedirs off

# audit se log file
sealert -a /var/log/audit/audit.log
```
