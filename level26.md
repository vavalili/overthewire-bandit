# Level 26

## Explanation

We’re given a binary with setuid permissions that allows us to execute commands as another user. We need to use it to retrieve the password for Bandit Level 27 

## Solution
<pre>
bandit26@bandit:~$ ls
bandit27-do  text.txt
bandit26@bandit:~$ ./bandit27-do
Run a command as another user.
  Example: ./bandit27-do id
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
</pre>
