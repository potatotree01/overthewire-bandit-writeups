# Bandit Level 7 -> Level 8

## Objective

Search the file `data.txt` for the password for the next level, which is next to the word `millionth`.

## Login

```bash
ssh -p 2220 bandit7@bandit.labs.overthewire.org
```

Password: `Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3`

## Commands Used

- `ls`
- `grep "millionth" data.txt`

## Solution

I used `ls` to confirm that `data.txt` was in the current working directory. Then, I used `grep "millionth" data.txt`, a command that searches a file (`data.txt`) for a specified pattern (`millionth`). This command returned the matching line with the next level's password next to `millionth`, separated by whitespace.
