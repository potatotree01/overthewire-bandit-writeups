# Bandit Level 20 -> Level 21

## Objective

In the home directory, there is a setuid binary that accomplishes the following:

1. Connects to localhost on the port specified as a command-line argument
2. Reads a line of text from the connection and compares it to the password for user `bandit20`
3. If the password and line of text are matching, then it will transmit the password for the next level

Note: Try connecting to your own network daemon to see if it works as expected.

## Login

```bash
ssh -p 2220 bandit20@bandit.labs.overthewire.org
```

Password: `4pIjcunZ0fK2vmp3IwfG8Vf7VhxD6pOA`

## Commands Used

- `ls`
- `tmux`
- `echo "4pIjcunZ0fK2vmp3IwfG8Vf7VhxD6pOA" | nc -lvp 2222`
- `./suconnect 2222`

## Solution

I used `ls` and discovered that `suconnect` was the name of the setuid binary. Afterward, I used `tmux` to create a session and a window with two side-by-side panes, allowing me to easily achieve what I had planned next. I then used Netcat (`nc`) to start a TCP server that listens on port 2222 and sends the password for user `bandit20` to connecting clients, with the command `echo "4pIjcunZ0fK2vmp3IwfG8Vf7VhxD6pOA" | nc -lvp 2222`. Lastly, I used `./suconnect 2222` to connect to localhost on port 2222, read the line of text from the connection, and send over the password for the next level to the server.
