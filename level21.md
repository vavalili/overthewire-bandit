# Level 21

## Explanation

A program is automatically running at regular times using cron which is a time-based job scheduler , we have to look in /etc/cron.d/ for the configuration and see what command is being executed .

## Solution
<pre>
bandit21@bandit:~$ ls /etc/cron.d/
behemoth4_cleanup  cronjob_bandit22  cronjob_bandit24  leviathan5_cleanup    otw-tmp-dir
clean_tmp          cronjob_bandit23  e2scrub_all       manpage3_resetpw_job  sysstat
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
</pre>

- `ls /etc/cron.d/` List cron configuration files
- `cat /usr/bin/cronjob_bandit22.sh` Check the script that cron runs :
This script does two things:
1. Changes permissions of a file in /tmp so anyone can read it.
2. Copies the password for Bandit 22 into that file.
- `cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv` Read the password from the temporary file
