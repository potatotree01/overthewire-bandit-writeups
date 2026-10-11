# Bandit Level 9 -> Level 10

## Objective

Search the file `data.txt` for the password, which is preceded by "=" characters and is one of the few human-readable strings.

## Login

```bash
ssh -p 2220 bandit9@bandit.labs.overthewire.org
```

Password: `EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl`

## Commands Used

- `ls`
- `strings data.txt | grep "==="`

## Solution

I first used `ls` to confirm that `data.txt` was in the current working directory. Then, I used `strings data.txt` to search for human-readable strings and piped the output into `grep "==="` to search for strings preceded by three consecutive "=" characters, making the full command `strings data.txt | grep "==="`.
