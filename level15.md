# Level 15

## Explanation

To get the password for the next level we need to send the current password to port 30001 on localhost, but this time using SSL/TLS encryption.

## Solution
<pre>
bandit15@bandit:~$ openssl s_client -connect localhost:30001
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
Correct!
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
</pre>


- `openssl s_client` opens a secure connection

- `-connect localhost:30001`  tells it to connect to port 30001 on your own machine