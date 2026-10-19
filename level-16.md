# Bandit Level 16 -> Level 17

## Objective

The credentials for the next level can be retrieved by submitting the current level's password to a port in the range 31000 to 32000 on `localhost`. Figure out which of these ports has a server listening on it and supports SSL/TLS. There is only one server that will return the credentials; the others will simply echo back whatever was sent.

## Login

```bash
ssh -p 2220 bandit16@bandit.labs.overthewire.org
```

Password: `kS0Hf0u5HiXFwKMKFqXvPdOTNGGa0X8V`

## Commands Used

- `nmap -sV -T5 -p 31000-32000 localhost`
- `echo "kS0Hf0u5HiXFwKMKFqXvPdOTNGGa0X8V" | openssl s_client -quiet -connect localhost:31790`

## Solution

I used `nmap -sV -T5 -p 31000-32000 localhost` to scan ports 31000-32000 on `localhost` for services at a faster pace. After identifying port 31790 as the only open port that supports SSL/TLS and does not echo back whatever is sent to it, I used `echo "kS0Hf0u5HiXFwKMKFqXvPdOTNGGa0X8V" | openssl s_client -quiet -connect localhost:31790` to establish a TLS-encrypted connection to the port and submit the current level's password. The command returned an SSH private key, which serves as the credentials for the next level. 
