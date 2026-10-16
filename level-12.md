# Bandit Level 12 -> Level 13

## Objective

The file containing the password for the next level, `data.txt`, is a hexdump of a file that has been repeatedly compressed. It may be worth creating a directory with a difficult-to-guess name under `/tmp`, using `mkdir` or, better yet, `mktemp -d`, to work in. Then, copy `data.txt` using `cp` and move it into the temporary directory. Use `mv` to rename the file.

## Login

```bash
ssh -p 2220 bandit12@bandit.labs.overthewire.org
```

Password: `GROozWPO8QyN0mGrjUkID0WCYkZiQxrN`

## Commands Used

### Create a Temporary Directory & Copy the File
- `ls`
- `mktemp -d`
- `cp data.txt /tmp/tmp.5UxO3Z2gOC/`
- `cd /tmp/tmp.5UxO3Z2gOC`

### Reverse the Hexdump
- `xxd -r data.txt > data`

### Identify, Extract, and Decompress the File
- `file data`
- `mv data data.gz`
- `gzip -d data.gz`
- `mv data data.bz2`
- `bzip2 -d data.bz2`
- `mv data data.tar`
- `tar -xvf data.tar`
- `file data5.bin`
- `mv data5.bin data5.tar`
- `tar -xvf data5.tar`
- `file data6.bin`
- `mv data6.bin data6.bz2`
- `bzip2 -d data6.bz2`
- `file data6`
- `mv data6 data6.tar`
- `tar -xvf data6.tar`
- `file data8.bin`
- `mv data8.bin data8.gz`
- `gzip -d data8.gz`
- `file data8`
- `cat data8`

## Solution

I used `mktemp -d` to create a temporary directory with a unique name and `cp data.txt /tmp/tmp.5UxO3Z2gOC/` to copy `data.txt` into it. Then, I moved into the temporary directory and used `xxd -r data.txt > data` to convert the hexdump `data.txt` back into its original binary form, saving it as a file named `data`. Following this, I used `file` to identify the file type of `data` and renamed it with the appropriate file extension (`.gz`) using `mv`. I then used `gzip -d data.gz` to decompress this file. I repeated this process of identifying, renaming, and decompressing or extracting the file, making use of commands such as `gzip`, `bzip2`, and `tar`, until I reached the final file which contained human-readable ASCII text. Finally, I used `cat data8` to display the file's contents and retrieve the password for the next level. 
