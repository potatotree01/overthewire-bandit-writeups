# Bandit Level 3 -> Level 4

## Objective

Navigate to the `inhere` directory and locate a hidden file. Print out the hidden file's contents to retrieve the password for the next level.

## Login

```bash
ssh -p 2220 bandit3@bandit.labs.overthewire.org
```

Password: `7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME`

## Commands Used

- `ls`
- `ls -a ./inhere`
- `cat ./inhere/...Hiding-From-You`

## Solution

I used `ls` to find the `inhere` directory. After locating it, I used `ls -a ./inhere` with the `-a` option to reveal the hidden file in the `inhere` directory. Upon discovering the file `...Hiding-From-You`, I used `cat ./inhere/...Hiding-From-You` to print out its contents and get the password.
