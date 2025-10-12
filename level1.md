# Level 1

## Explanation 
 
 For this level we are told that the password for the next level is in a file called `-` 
The cat commande will try to interpret the - as a flag and not a file name.


 ## solution
<pre>
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
</pre>

- ``cat ./-`` Bash interprets - as standard input not a filename. So to avoid confusion, you prefix it with ./ to say
