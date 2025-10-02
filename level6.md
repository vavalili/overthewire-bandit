# Level 6

## Explanation

In this level the password is told to be in a file
- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

## Solution 
<pre>
bandit6@bandit:~$ find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
</pre>


- `/`	Start searching from the root of the file system.
- `type f`	Look only for files (not directories).
- `user` bandit7	Find files owned by the user bandit7.
- `group bandit6` Find files that belong to the group bandit6.
- `size 33c`	Find files that are exactly 33 bytes in size (c means bytes).
- `2>/dev/null`	Hide error messages (like permission denied) so the output is cleaner.