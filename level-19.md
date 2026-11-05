# Bandit Level 19 -> Level 20

## Objective

The setuid binary in the home directory should be used to get the password for the next level which can be found in the usual place (`/etc/bandit_pass`). Execute the file without any arguments to figure out how to use it.

## Login

```bash
ssh -p 2220 bandit19@bandit.labs.overthewire.org
```

Password: `KpsOfPkcP7i1FlIExk2QEjyt6dw8dxZI`

## Commands Used

- `ls`
- `./bandit20-do`
- `./bandit20-do ls /etc/bandit_pass`
- `./bandit20-do cat /etc/bandit_pass/bandit20`

## Solution

I used `ls` and confirmed that `bandit20-do`, the setuid binary, was in the home directory. Then, following the instructions, I executed the setuid binary with `./bandit20-do` and found out that it allows you to run a command with the privileges of the file's owner (`bandit20`) and the syntax to do so. Afterward, I used `./bandit20-do ls /etc/bandit_pass` to confirm the names of the files in `/etc/bandit_pass`. Lastly, I ran `./bandit20-do cat /etc/bandit_pass/bandit20` to retrieve the password for the next level.
