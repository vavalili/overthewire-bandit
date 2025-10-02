# Level 13

## Explanation

In this level we don’t receive the password for the next level directly instead we are given a private SSH key (sshkey.private) that allows us to log in as user bandit14.

## Solution 
<pre>
bandit13@bandit:~$ ls
sshkey.private
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost -p 2220
</pre>

- `-i sshkey.private` specifies the private key to use for authentication
- `-p 2220`  port number used by OverTheWire for SSH connections