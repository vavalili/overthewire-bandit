# Level 29

## Explanation

In this level, we clone a Git repository and explore its branches to find the password for the next level

## Solution
<pre>
bandit29@bandit:~$ mkdir /tmp/level29
bandit29@bandit:~$ cd /tmp/level29
bandit29@bandit:/tmp/level29$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
bandit29@bandit:/tmp/level29$ ls
repo
bandit29@bandit:/tmp/level29$ cd repo
bandit29@bandit:/tmp/level29/repo$ ls
README.md
bandit29@bandit:/tmp/level29/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>
bandit29@bandit:/tmp/level29/repo$ git branch -r
  origin/HEAD -> origin/master
  origin/dev
  origin/master
  origin/sploits-dev

bandit29@bandit:/tmp/level29/repo$ git checkout dev
branch 'dev' set up to track 'origin/dev'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/level29/repo$ ls
code  README.md
bandit29@bandit:/tmp/level29/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
</pre>


- ``git branch -r`` used to list all remote branches in a Git repository.
- ``git checkout dev`` tells Git to switch your working directory to the branch named dev

