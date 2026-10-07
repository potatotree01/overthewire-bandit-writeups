# Bandit Level 1 -> Level 2

## Objective

Locate the file named `-` in the home directory and retrieve the password for the next level in it.

## Login

```bash
ssh -p 2220 bandit1@bandit.labs.overthewire.org
```

Password: `6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR`

## Commands Used
- `ls`
- `cat ./-`

## Solution

I used `ls` to print out the home directory's contents. A file called `-` appeared, so I used `cat ./-` to print out its contents. The command `cat -` is not used because it waits for further user input instead of treating `-` as a filename; `cat ./-` is used because the `./-` specifies that `-` is a file in the current working directory.
