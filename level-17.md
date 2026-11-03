# Bandit Level 17 -> Level 18

## Objective

In the home directory, there are two files: `passwords.old` and `passwords.new`. The file `passwords.new` contains the password for the next level, which is the only line that has been changed between the two files.

## Login

```bash
chmod 600 b17-private.key
ssh -i b17-private.key -p 2220 bandit17@bandit.labs.overthewire.org
```

Note: `b17-private.key` is the SSH private key saved from the previous level.

## Commands Used

- `ls`
- `diff passwords.old passwords.new`

## Solution

I used `ls` to confirm the files' existence in the home directory. Then, I used `diff passwords.old passwords.new` to compare the two files and identify their differences. The output revealed the changed line, which contained the password for the next level.
