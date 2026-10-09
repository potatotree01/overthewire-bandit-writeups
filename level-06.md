# Bandit Level 6 -> Level 7

## Objective

The password for the next level is stored somewhere on the server in an object that is owned by user `bandit7`, owned by group `bandit6`, and 33 bytes in size.

## Login

```bash
ssh -p 2220 bandit6@bandit.labs.overthewire.org
```

Password: `pXa26xhMWaC2SvDotA4r9EgZkulOeSBW`

## Commands Used

- `find / -user bandit7 -group bandit6 -size 33c 2>/dev/null`
- `cat /var/lib/dpkg/info/bandit7.password`

## Solution

I used `find / -user bandit7 -group bandit6 -size 33c 2>/dev/null` to search the filesystem starting from `/`, the root directory, for an object that was owned by the user `bandit7`, belonged to the group `bandit6`, and was 33 bytes in size. I included `2>/dev/null` so that error messages would be redirected to `/dev/null` and omitted from the output. The command returned `/var/lib/dpkg/info/bandit7.password`, so I used `cat /var/lib/dpkg/info/bandit7.password` to print out the file's contents and retrieve the password for the next level.
