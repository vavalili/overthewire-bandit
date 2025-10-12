# Level 30

## Explanation

In this level, we clone a Git repository and inspect its tags to locate the password for the next level.

## Solution
<pre>
bandit30@bandit:~$ mkdir /tmp/level30
bandit30@bandit:~$ cd /tmp/level30
bandit30@bandit:/tmp/level30$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
bandit30@bandit:/tmp/level30$ ls
repo
bandit30@bandit:/tmp/level30$ cd repo
bandit30@bandit:/tmp/level30/repo$ ls
README.md
bandit30@bandit:/tmp/level30/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/level30/repo$ git tag
secret
bandit30@bandit:/tmp/level30/repo$ git show secret
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
</pre>

- ``git tag`` Lists all tags in the current Git repository
- ``git show secret`` Displays the content that the tag secret points to


