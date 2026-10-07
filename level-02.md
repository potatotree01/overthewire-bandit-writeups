# Bandit Level 2 -> Level 3

## Objective

Locate a file called `--spaces in this filename--` in the home directory and print out its contents to retrieve the password for the next level.

## Login
```bash
ssh -p 2220 bandit2@bandit.labs.overthewire.org
```

Password: `PK8fYLZg2hnHSz83plBL1iEPKdD3QToB`

## Commands Used

- `ls`
- `cat -- "--spaces in this filename--"`

## Solution

I used `ls` to print out the contents of the home directory, verifying that a file named `--spaces in this filename--` exists. Afterward, I used `cat -- "--spaces in this filename--"` to print out the file's contents; quotation marks are used to keep `--spaces in this filename--` together as one argument and  `--` is used because it indicates the end of options, ensuring that `--spaces in this filename--` is not treated as an option. 
