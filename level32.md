# Level 32

## Explanation

In this level, we’re dropped into a custom shell that turns all commands into uppercase, making normal commands fail we need to escape this shell in orded to find the password for the next level 

## Solution
<pre>
WELCOME TO THE UPPERCASE SHELL
>> ls
sh: 1: LS: Permission denied
>> $0
$ ls
uppershell
$ whoami
bandit33
$ cat /etc/bandit_pass/bandit33
tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
</pre>

- ``$0`` executed the default shell escaping the uppercase shell.
