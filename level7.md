# Level 7

## Explanation 

For this level the password is stored in the file data.txt next to the word millionth

## Solution
<pre>
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
</pre>

- `cat data.txt` Reads and displays the entire content of the file data.txt.

- `grep millionth` Filters the output and shows only the line that contains the word millionth