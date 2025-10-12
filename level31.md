# Level 31

## Explanation

In this level we clone a Git repository and push a file called key.txt with the content “May I come in?” to the master branch. Once pushed, the server gives us the password for the next level.

## Solution
<pre>
bandit31@bandit:~$ mkdir /tmp/level31
bandit31@bandit:~$ cd /tmp/level31
bandit31@bandit:/tmp/level31$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
bandit31@bandit:/tmp/level31$ ls
repo
bandit31@bandit:/tmp/level31$ cd repo
bandit31@bandit:/tmp/level31/repo$ ls
README.md
bandit31@bandit:/tmp/level31/repo$ cat README.md
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master
bandit31@bandit:/tmp/level31/repo$ echo 'May I come in?' > key.txt
bandit31@bandit:/tmp/level31/repo$ cat .gitignore
*.txt
bandit31@bandit:/tmp/level31/repo$ git add -f key.txt
bandit31@bandit:/tmp/level31/repo$ git commit -m "Add key.txt with password request"
[master 9fd569f] Add key.txt with password request
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
bandit31@bandit:/tmp/level31/repo$ git push
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit31-git@localhost's password:
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 343 bytes | 343.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Well done! Here is the password for the next level:
remote: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
</pre>


- ``echo 'May I come in?' > key.txt`` Creates the required file with the correct content
- ``cat .gitignore`` Reveals that *.txt files are ignored by Git  key.txt would normally be skipped
- ``git add -f key.txt`` Force-adds the file despite .gitignore rules
- ``git commit -m "Add key.txt with password request`` Commits the file to the local master branch
- ``git push`` push the commit to the remote repo