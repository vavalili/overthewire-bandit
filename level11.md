# Level 11

## Explanation

The password is stored in the file data.txt where all letters have been rotated by 13 positions

## Solution 
<pre>
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
</pre>


- `cat data.txt` this reads and displays the contents of the file data.txt.
- `tr 'A-Za-z' 'N-ZA-Mn-za-m'` this replaces each letter with the one 13 positions later in the alphabet.

