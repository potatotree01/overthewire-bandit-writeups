# Bandit Level 15 -> Level 16

## Objective

The password for the next level can be found by submitting the current level's password to port 30001 on `localhost` using SSL/TLS encryption.

## Login

```bash
ssh -p 2220 bandit15@bandit.labs.overthewire.org
```

Password: `pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7`

## Commands Used

- `echo "pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7" | openssl s_client -quiet -connect localhost:30001`

## Solution

I used `echo` and `|` to pipe the current level's password into `openssl s_client`, which establishes a TLS-encrypted connection to `localhost` on port 30001, to retrieve the password for the next level.
Alternative: The same task can be accomplished using `ncat --ssl localhost 30001`, which also establishes a TLS-encrypted connection.
