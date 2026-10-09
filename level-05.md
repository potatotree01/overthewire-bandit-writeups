# Bandit Level 5 -> Level 6

## Objective

Navigate to the `inhere` directory. Then, find a file under that directory that is human-readable, 1033 bytes in size, and not executable. Print out the file's contents to get the password for the next level.

## Login

```bash
ssh -p 2220 bandit5@bandit.labs.overthewire.org
```

Password: `6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG`

## Commands Used

- `cd inhere`
- `find . -type f -size 1033c ! -executable`
- `file ./maybehere07/.file2`
- `cat ./maybehere07/.file2`

## Solution

I used `cd inhere` to change the current working directory to `inhere`. Afterward, I used `find . -type f -size 1033c ! -executable` to locate the file with the stated properties. The `.` specifies where to search (the current working directory), `-type f` specifies to search for a file, `-size 1033c` specifies that the file is exactly 1033 bytes in size, and `! -executable` specifies that the current user cannot execute the file. The command returned `./maybehere07/.file2`, and I used `file ./maybehere07/.file2` to verify that the file contained human-readable text. Finally, I used `cat ./maybehere07/.file2` to retrieve the password.
