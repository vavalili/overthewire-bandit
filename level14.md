# Level 14

## Explanation

To get the password for the next level we need to send the current password (from /etc/bandit_pass/bandit14) to port 30000 on localhost

## Solution
<pre>
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
bandit14@bandit:~$ echo MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS | nc localhost 30000
Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
</pre>

- `echo` prints the password

- `|` sends it as input to nc

- `nc localhost 30000` connects to port 30000 on your local machine