# Level 17

## Explanation

We are given two files:
- passwords.old
- passwords.new
Only one line is different between them and is in passwords.new and contains the password for Level 18

## Solution 
<pre>
bandit17@bandit:~$ ls
passwords.new  passwords.old
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< gvE89l3AhAhg3Mi9G2990zGnn42c8v20
---
> x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
\pc>ssh -p 2220 bandit18@bandit.labs.overthewire.org
Byebye !
Connection to bandit.labs.overthewire.org closed
</pre>

- `diff passwords.old passwords.new` show you the difference between the two files 
note : The > symbol means this line is only in passwords.new