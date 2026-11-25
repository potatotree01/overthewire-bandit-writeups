# Bandit Level 22 -> Level 23

## Objective

Cron the time-based job scheduler, is running a program automatically at regular intervals. Check /etc/cron.d/ for the configuration and see what command is being executed.

Note: Being able to read and understand shell scripts written by others is a valuable skill. The script for this level was intentionally designed to be easy to understand. Try executing the script and seeing the debug information it prints, if you are having issues understanding what it does.

## Login

```bash
ssh -p 2220 bandit22@bandit.labs.overthewire.org
```

Password: `RYVux2rHEm9tiXHmLFzuR7Vhx6AZQMEz`

## Commands Used

- `ls -l /etc/cron.d/`
- `cat /etc/cron.d/cronjob_bandit23`
- `cat /usr/bin/cronjob_bandit23.sh`
- `echo "I am user bandit23" | md5sum | cut -d ' ' -f 1`
- `cat /tmp/8ca319486bfbbc3663ea0fbe81326349`

## Solution

Following the instructions, I used `ls -l /etc/cron.d/` to check the cron configuration files and found a file called `cronjob_bandit23`. I used `cat /etc/cron.d/cronjob_bandit23` to inspect it and discovered that `/usr/bin/cronjob_bandit23.sh` was running every minute. The script hashes the string "I am user $myname" using md5 and redirects `$myname`'s password to a temporary file whose name is the hashed string. To recreate the file name and get `bandit23`'s password, I used `echo "I am user bandit23" | md5sum | cut -d ' ' -f 1` (the same command in the script) which produced "8ca319486bfbbc3663ea0fbe81326349". Lastly, I ran `cat /tmp/8ca319486bfbbc3663ea0fbe81326349` and retrieved the password for the next level.
