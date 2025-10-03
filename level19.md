# Level 19

## Explanation

The password for Bandit 20 is stored in the usual location `/etc/bandit_pass/bandit20` but Bandit 19 doesn’t have permission to read it directly instead there’s a special file in the home directory called bandit20-do it’s a setuid binary which means it runs with the permissions of Bandit 20, even when executed by Bandit 19.


## Solution
<pre>
bandit19@bandit:~$ ls
bandit20-do
bandit19@bandit:~$ ./bandit20-do
Run a command as another user.
  Example: ./bandit20-do id
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
</pre>

- `./bandit20-do`  Runs the program without arguments and tells how to use it
- `./bandit20-do cat /etc/bandit_pass/bandit20` This runs cat /etc/bandit_pass/bandit20 as Bandit 20,

