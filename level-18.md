# Bandit Level 18 -> Level 19

## Objective

The password for the next level is in the file `readme` in the home directory, but `.bashrc` has been modified to log you out when you log in with SSH.

## Login

```bash
ssh -p 2220 bandit18@bandit.labs.overthewire.org cat readme
```

Password: `OQxXZjELndr90zuhOTDYBEomI0SZITXI`

## Commands Used

See the [Login](#login) section.

## Solution

I logged in as user `bandit18` using SSH while also specifying a command to run: `cat readme`. SSH allows you to execute commands remotely by specifying the command after the hostname. By doing so, I was able to print the contents of `readme` and retrieve the password for the next level.
