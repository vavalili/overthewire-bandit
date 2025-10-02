# Level 0

## Explanation 

The goal of this level is to connect to the server via ssh.
The provaded element are :
- the host server: bandit.labs.overthewire.org
- the username: bandit0
- the password : bandit0
- port number: 2220

When connected to the server we are told that the password to the next level is in a file called "readme"  

## Solution
<pre>
pc>ssh -p 2220 bandit0@bandit.labs.overthewire.org
bandit0@bandit:~$ cat readme
Congratulations on your first steps into the bandit game!!
Please make sure you have read the rules at https://overthewire.org/rules/
If you are following a course, workshop, walkthrough or other educational activity,
please inform the instructor about the rules as well and encourage them to
contribute to the OverTheWire community so we can keep these games free!
The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
</pre>





