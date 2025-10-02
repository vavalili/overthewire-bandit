# Level 10

## Explanation

The password is in the file `data.txt` that is encoded in Base64 format.  

## Solution
<pre>
bandit10@bandit:~$ base64 -d data.txt
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
</pre>

- `base64 -d` used to decode the file