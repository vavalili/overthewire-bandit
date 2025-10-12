# Level 27

## Explanation

In this level we will practice our git skills, we are given a remote repository that we have to clone and explore to find the password to the next level.

## Solution
<pre>
bandit27@bandit:~$ cd /tmp
bandit27@bandit:/tmp$ mkdir level27
bandit27@bandit:/tmp$ cd level27
bandit27@bandit:/tmp/level27$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
bandit27-git@localhost's password:  ## same password as level 27
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/level27$ ls
repo
bandit27@bandit:/tmp/level27$ cd repo
bandit27@bandit:/tmp/level27/repo$ ls
README
bandit27@bandit:/tmp/level27/repo$ cat README
The password to the next level is: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
</pre>

- ``git clone``	Tells Git to copy a remote repository to the local machine
- ``ssh://`` Specifies that the connection will use the SSH protocol
- ``bandit27-git@localhost`` Username (bandit27-git) and host (localhost) — 
- ``:2220``	The port number — Bandit uses port 2220 instead of the default SSH port (22)
- ``/home/bandit27-git/repo`` The path to the Git repository on the remote server