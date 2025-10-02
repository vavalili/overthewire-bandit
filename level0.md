# Level0

## Explanation 

The goal of this level is to connect to the server via ssh.
The provaded element are :
- the host server: bandit.labs.overthewire.org
- the username: bandit0
- the password : bandit0
- port number: 2220

When connected to the server we are told that the password to the next level is in a file called "readme"  

## Solution

`ssh -p 2220 bandit0@bandit.labs.overthewire.org`
`ls`
`cat readme`
- ssh : Secure Shell Protocol to connect romotly.
- -p 2220 : specifies the port number.
- ls : used to list the files and directories.
- cat : use it to display the contents of a file directly in the terminal.




