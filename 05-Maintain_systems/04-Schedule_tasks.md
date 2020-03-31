# Schedule Tasks Using at and cron

## at utility
```sh
# install at
yum install at
systemctl enable --now atd

# shedule with at in 5 minutes
at now +5 min 

# shedule with at in 5 hours
at now +5 hours

# shedule with at in 5 days
at now +5 days

# schedule regurarly
at 12:00am
# press enter and write a command and finally press Ctrl-d

# see at jobs
atq

# remove a job
atrm 1 # press job number

# at uses a file 'at.deny' or 'at.allow' to manage who can uses at to schedule commands
```

## cron utility
```sh
# cron file
nano /etc/crontab

# For details see man 4 crontabs
# Example of job definition:
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  * user-name  command to be executed

# cron.d for custom scripts in different time
# cron.hourly execute every hour as the same as cron.daily, cron.monthly, cron.weekly
# cron is for regular users

# anacron is for only privileged users
# anacron is a utility that allows us to run a command after a given number 
# of days if it has not run
# anacron file
nano /etc/anacrontab

# struct of anacrontab file
# period in days   delay in minutes   job-identifier   command

# force to run all jobs ingnoring the delay
anacron -n
```


