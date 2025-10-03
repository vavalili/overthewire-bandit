# Level 22

## Explanation

A script is running automatically at regular times using cron, a tool that schedules tasks the goal is to look inside the folder /etc/cron.d/ to find out which command is being executed and what it does.

## Solution
<pre>
bandit22@bandit:~$ ls /etc/cron.d/
behemoth4_cleanup  cronjob_bandit22  cronjob_bandit24  leviathan5_cleanup    otw-tmp-dir
clean_tmp          cronjob_bandit23  e2scrub_all       manpage3_resetpw_job  sysstat
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat  /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ echo I am user bandit23 | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
</pre>

- ``ls /etc/cron.d/`` List cron jobs
- ``cat /etc/cron.d/cronjob_bandit23`` View the cron job configuration
- ``cat /usr/bin/cronjob_bandit23.sh`` Read the script
This script:
1. Gets the current username (bandit23)
2. Creates a hash from the phrase I am user bandit23
3. Uses that hash as a filename in /tmp
4. Copies the password file for bandit23 into that file
- ``echo I am user bandit23 | md5sum | cut -d ' ' -f 1`` Generate the hash manually
- ``cat /tmp/8ca319486bfbbc3663ea0fbe81326349`` Read the password from the generated file



