# Bandit Level 8 -> Level 9

## Objective

The file `data.txt` contains the password for the next level, which is the only line of text that appears exactly once.

## Login

```bash
ssh -p 2220 bandit8@bandit.labs.overthewire.org
```

Password: `VR1ljMayciFxbnUokuQmJFw6QC9VKtub`

## Commands Used

- `ls`
- `sort data.txt | uniq -u`

## Solution

I used `ls` to confirm that `data.txt` was in the current working directory. Afterward, I used `sort data.txt | uniq -u`, which returned the unique line containing the password. The `sort data.txt` component sorts the contents of `data.txt` alphabetically or numerically (this is necessary because `uniq` only detects adjacent duplicate lines). The pipe (`|`) uses the output of `sort data.txt` as the input for `uniq -u`. Lastly, `uniq -u` outputs lines that occur only once, omitting any lines that have duplicates.
