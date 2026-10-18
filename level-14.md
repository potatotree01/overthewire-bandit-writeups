# Bandit Level 14 -> Level 15

## Objective

The password for the next level can be found by submitting the current level's password to port 30000 on `localhost`.

## Login

```
ssh -p 2220 bandit14@bandit.labs.overthewire.org
```

Password: `aaWecNkG4FhxJQxz07uiwzVP6bJiYS65`

## Commands Used

- `nc localhost 30000`

## Solution

I connected to the server as `bandit14`, then ran `nc localhost 30000` to connect to port 30000 on the local machine. The `nc` (Netcat) command requires only the destination hostname and port number as arguments to establish a connection, so no additional arguments were needed. Next, I entered the current level's password, retrieving the password for the next level.
