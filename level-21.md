# Bandit Level 21 -> Level 22

## Objective

Cron, the time-based job scheduler, is running a program automatically at regular intervals. Check /etc/cron.d/ for the configuration and see what command is being executed.

## Login

```bash
ssh -p 2220 bandit21@bandit.labs.overthewire.org
```

Password: `bW9kBv5WC3P4yoDyf12LSdGuNz5ka6hY`

## Commands Used

- `ls -l /etc/cron.d/`
- `cat /etc/cron.d/cronjob_bandit22`
- `cat /usr/bin/cronjob_bandit22.sh`
- `cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`

## Solution

I used `ls -l /etc/cron.d/` to see the cron configuration files and noticed a file called `cronjob_bandit22`. I ran `cat /etc/cron.d/cronjob_bandit22` and found that a script called `cronjob_bandit22.sh` was being executed every minute. Using `cat /usr/bin/cronjob_bandit22.sh` to check its contents, I discovered that the contents of `/etc/bandit_pass/bandit22` were being redirected to `/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`. Finally, I used `cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv` to retrieve the password for the next level.
