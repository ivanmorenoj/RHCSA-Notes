# Change Passwords and Adjust Password Aging for Local User Accounts

```sh
# password file stored
/etc/shadow

# user file 
/etc/passwd

# see password expiration
chage -l user

# set account expire day
chage -E 2020-06-05

# set password expire in 90 days
chage -M 90 user

# remove expire day for account
chage -M -1 user

# set inactivity number of days
chage -I 5 user1
```
