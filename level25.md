# Level 25

## Explanation

When we log in to bandit26 we don’t get a normal shell — instead, a program called showtext runs and then exits. the goal is to break out of that program and get access to a real shell.

## Solution
<pre>
bandit25@bandit:~$ ls
bandit26.sshkey
bandit25@bandit:~$ ssh -i bandit26.sshkey -p 2220 bandit26@bandit.labs.overthewire.org
Connection to bandit.labs.overthewire.org closed.
# connection closed immediatly
bandit25@bandit:~$ cat /etc/passwd | grep bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext # no regular shell
bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0
# Make terminal small so text doesn't fit on one screen
bandit25@bandit:~$ ssh -i bandit26.sshkey -p 2220 bandit26@bandit.labs.overthewire.org
# Press v to enter vim editor from more
# Press Esc then type :set shell=/bin/bash
# Type :shell to get a real bash shell
# we have to resize the terminal for it to not display the entire text.txt at once
bandit26@bandit:~$ cat /etc/bandit_pass/bandit26
s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ
</pre>



- ``cat /etc/passwd | grep bandit26`` Shows the login shell for bandit26
- ``cat /usr/bin/showtext`` Reveals the script
- ``v`` This opens the file in vi editor
- ``Esc``  to enter command mode
- ``:set shell=/bin/bash``  sets the shell to bash
- ``:shell``  launches a real bash shell