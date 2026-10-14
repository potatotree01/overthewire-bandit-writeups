# Bandit Level 11 -> Level 12

## Objective

The file `data.txt` contains the password for the next level. All lowercase (a-z) and uppercase (A-Z) letters have been shifted by 13 positions.

## Login

```bash
ssh -p 2220 bandit11@bandit.labs.overthewire.org
```

Password: `pYfOY6HwUsDj5rL9UvyhU7MCmv8vN5Ro`

## Commands Used

- `ls`
- `tr "A-Za-z" "N-ZA-Mn-za-m" < data.txt`

## Solution

I used `ls` to confirm that `data.txt` was in the current working directory. Given that all lowercase and uppercase letters had been rotated by 13 positions, I determined that the ROT13 cipher had been used to encode `data.txt`. Accordingly, I used `tr "A-Za-z" "N-ZA-Mn-za-m" < data.txt`, where each letter in "A-Za-z" is mapped to its corresponding letter in "N-ZA-Mn-za-m" and `data.txt` is used as input for the command, to apply the ROT13 cipher to the file and retrieve the password.
