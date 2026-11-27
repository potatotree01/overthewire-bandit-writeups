# Bandit Level 23 -> Level 24

## Objective

Cron, the time-based job scheduler, is running a program automatically at regular intervals. Check /etc/cron.d/ for the configuration and see what command is being executed.

Note: This level requires you to create your own shell script.
Note 2: Remember that your shell script is removed after it is executed, so you may want to keep a copy.

## Login

```bash
ssh -p 2220 bandit23@bandit.labs.overthewire.org
```

Password: `gKXDTAXnIz3OBxiPjRZ2uqutUlPZrBsw`

## Solution

I started by checking the `/etc/cron.d/` directory to see the scheduled tasks that were configured.
```bash
ls -l /etc/cron.d/
```

I found a file named `cronjob_bandit24` and decided to inspect its contents to understand what it does.
```bash
cat /etc/cron.d/cronjob_bandit24
```

The cronjob executes a script called `/usr/bin/cronjob_bandit24.sh` every minute, so I decided to inspect it to see what it does. Its contents indicated that it attempts to execute files owned by `bandit23` in `/var/spool/bandit24/foo` and deletes them afterward.
```bash
cat /usr/bin/cronjob_bandit24.sh
```

I need to create a script that retrieves the password of `bandit24`, which is stored in `/etc/bandit_pass/bandit24`. I'll create it in `/tmp`, since this directory allows me to create and edit files.
```bash
touch /tmp/solve.sh
nano /tmp/solve.sh
```

Inside the script, I will redirect the contents of `/etc/bandit_pass/bandit24` into a file called `/tmp/bandit24_passwd.txt`, which I will be able to read after the script is executed.
```bash
#!/bin/bash

cat /etc/bandit_pass/bandit24 > /tmp/bandit24_passwd.txt
```

Now I need to make the script executable so that the scheduled cronjob can run it.
```bash
chmod +x /tmp/solve.sh
```

Since the script executed by the cronjob checks for files in `/var/spool/bandit24/foo`, I need to copy my script into that directory for it to be executed.
```bash
cp /tmp/solve.sh /var/spool/bandit24/foo/
```

After the script has been executed, the password file should have been created, so I can just read its contents to retrieve the password.
```bash
cat /tmp/bandit24_passwd.txt
```
