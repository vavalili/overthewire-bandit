# Level 27

## Explanation

To find the password for the next level we have to clone and explore a git repository.

## Solution
<pre>
bandit28@bandit:~$ cd /tmp
bandit28@bandit:/tmp$ mkdir level28
bandit28@bandit:/tmp$ cd level28
bandit28@bandit:/tmp/level28$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
bandit28-git@localhost's password: ## same password as level 28
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 9 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (9/9), done.
Resolving deltas: 100% (2/2), done.
bandit28@bandit:/tmp/level28$ ls
repo
bandit28@bandit:/tmp/level28$ cd repo
bandit28@bandit:/tmp/level28/repo$ ls
README.md
bandit28@bandit:/tmp/level28/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/level28/repo$ git log
commit 710c14a2e43cfd97041924403e00efb00b3a956e (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Fri Aug 15 13:16:10 2025 +0000

    fix info leak

commit 68314e012fbaa192abfc9b78ac369c82b75fab8f
Author: Morla Porla <morla@overthewire.org>
Date:   Fri Aug 15 13:16:10 2025 +0000

    add missing data

commit a158f9a82c29a16dcea474458a5ccf692a385cd4
Author: Ben Dover <noone@overthewire.org>
Date:   Fri Aug 15 13:16:10 2025 +0000

    initial commit of README.md
bandit28@bandit:/tmp/level28/repo$ git checkout 68314e012fbaa192abfc9b78ac369c82b75fab8f
Note: switching to '68314e012fbaa192abfc9b78ac369c82b75fab8f'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 68314e0 add missing data
bandit28@bandit:/tmp/level28/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7    
</pre>


- ``git log`` This command shows the commit history of a Git repository
- ``git checkout 68314e012fbaa192abfc9b78ac369c82b75fab8f`` This command tells Git to switch the working directory to the exact state of the repository at the commit with hash 68314e012fbaa192abfc9b78ac369c82b75fab8f
