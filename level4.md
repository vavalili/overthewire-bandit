# Level 4

## Explanation
In this level the password is told to be in the only human-readable file in the inhere directory

## Solution
<pre>
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ file ./* | grep text
./-file00: Non-ISO extended-ASCII text, with no line terminators, with overstriking
./-file07: ASCII text
bandit4@bandit:~/inhere$ cat ./-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
</pre>

- ``file ./*`` tells the type of each file
- ``| grep text`` Filters the output to show only files that contain the word “text” in their type