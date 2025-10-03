# Level 20

## Explanation

To get the password for Bandit 21 there’s a special program in the home directory called suconnect That connects to localhost on the port we choose it reads one line of text from that connection. If the text matches the password from Bandit 20, it sends back the password for Bandit 21

## Solution
<pre>
bandit20@bandit:~$ ls
suconnect
bandit20@bandit:~$ ./suconnect
Usage: ./suconnect <portnumber>
This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back.
bandit20@bandit:~$ nc -l -p 12345
./suconnect 12345
Read: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
Password matches, sending next password
</pre>


 At the same time from another tab 
 <pre>
bandit20@bandit:~$ ./suconnect 12345
Read: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
Password matches, sending next password
</pre>


- `nc -l -p 12345` This opens port 12345 and waits for a connection it will act as the “server” that suconnect will connect to
- `./suconnect 12345` This connects to the netcat listener on port 12345
- Sends the Bandit 20 password and waits for a response 

