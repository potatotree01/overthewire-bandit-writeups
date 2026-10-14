# Bandit Level 10 -> Level 11

## Objective

The file `data.txt` contains the password for the next level which is encoded using Base64.

## Login

```bash
ssh -p 2220 bandit10@bandit.labs.overthewire.org
```

Password: `B0s2khmbT9u0geKuOoVGW3JZKhndE3BG`

## Commands Used

- `ls`
- `base64 -d data.txt`

## Solution

I used `ls` to check that `data.txt` was in the current working directory. Then, because I know that `data.txt` contains Base64 encoded data, I decoded the password in it using `base64` with the `-d` option, making the full command `base64 -d data.txt`.
