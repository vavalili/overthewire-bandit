# Level 5

## Explanation
In this level the password is in a file that is :
- human-readable
- 1033 bytes in size
- not executable

## Solution
<pre>
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16  maybehere19
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17
bandit5@bandit:~/inhere$ find -type f -size 1033c ! -executable
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
</pre>


- ``find`` search for files
- ``-type f`` only regular files
- ``-size 1033c`` exactly 1033 bytes
- ``! -executable`` not executable 