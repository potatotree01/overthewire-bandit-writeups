# Bandit Level 0 -> Level 1

## Objective

Locate the file named `readme` in the home directory and print out its contents to retrieve the password for the next level.

## Login

```bash
ssh -p 2220 bandit0@bandit.labs.overthewire.org
```

Password: `bandit0`

## Commands Used

- `ls`
- `cat readme`

## Solution

I noticed that I was in the home directory and used `ls` to list its contents. A file called `readme` appeared, so I used `cat readme` to print out and obtain the password for the next level.
