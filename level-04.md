# Bandit Level 4 -> Level 5

## Objective

Navigate to the `inhere` directory and find the only human-readable file. Print out the file's contents to get the password for the next level.

## Login

```bash
ssh -p 2220 bandit4@bandit.labs.overthewire.org
```

Password: `xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq`

## Commands Used

- `ls`
- `cd inhere`
- `file ./*`
- `cat ./-file07`

## Solution

I used `ls` to locate the `inhere` directory and `cd inhere` to move to it. Then I used `ls` again and discovered ten files, each in the format `-file0X` where X ranges from zero to nine. Afterward, I used `file ./*` to identify the file type of each file based on its contents and noticed that `-file07` was the only file identified as ASCII text (human-readable text). Lastly, I used `cat ./-file07` to retrieve the password in the file.
