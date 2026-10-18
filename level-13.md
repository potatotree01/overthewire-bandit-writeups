# Bandit Level 13 -> Level 14

## Objective

The password for the next level is in `/etc/bandit_pass/bandit14`, which can only be read by user `bandit14`. A private SSH key is provided, instead of a password, and can be used to log into the next level. Figure out how to use the key for this level by considering commands used to log into previous levels. A hint file is provided for assistance and can be found in the home directory. Error messages should be read as they are informative.

## Login

```bash
ssh -p 2220 bandit13@bandit.labs.overthewire.org
```

Password: `qQYQiHOBPR8zR61qxYqX45quvihF2uzk`

## Commands Used

- `ls`
- `exit`
- `scp -P 2220 bandit13@bandit.labs.overthewire.org:/home/bandit13/sshkey.private .`
- `chmod 600 sshkey.private`
- `ssh -i sshkey.private -p 2220 bandit14@bandit.labs.overthewire.org`
- `cat /etc/bandit_pass/bandit14`

## Solution

I first used `ls` to identify the filename of the SSH private key, while logged in as `bandit13`. Then, I logged out using `exit` and used `scp -P 2220 bandit13@bandit.labs.overthewire.org:/home/bandit13/sshkey.private .` to securely copy `sshkey.private` from the remote server to my current local directory. Afterward, I changed its permissions using `chmod 600 sshkey.private`, allowing only the file's owner to read and write it. This prevents SSH from rejecting the key because its permissions are too open. Next, I logged in as `bandit14` using `ssh -i sshkey.private -p 2220 bandit14@bandit.labs.overthewire.org` and retrieved the password for the next level by running `cat /etc/bandit_pass/bandit14`.
