# Level 2

## Explanation

Similar to the previous level, we are told that the password for the next level is stored in a file named `--spaces in this filename--`, which the cat command cannot read directly because of the special characters in its name.

## Solution
<pre>
bandit2@bandit:~$ ls
--spaces in this filename--
bandit2@bandit:~$ cat "./--spaces in this filename--"
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
</pre>

- ``cat "./--spaces in this filename--"`` Without quotes the shell would split it into multiple arguments