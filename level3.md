# Level 3

## Explanation

In this level we are told that the password is in a hidden  file inside the `hidden` directory
However when using the `ls` command to list the content of the directory nothing appears.
## Solution
<pre>
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -a
.  ..  ...Hiding-From-You
bandit3@bandit:~/inhere$ cat ...Hiding-From-You
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
</pre>