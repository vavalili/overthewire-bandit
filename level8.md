# Level 8

## Explanation

The password is stored in the file data.txt and is the only line of text that occurs only once

## Solution 
<pre>
bandit8@bandit:~$ sort data.txt | uniq -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
</pre>


- `sort data.txt` Organizes all the lines in data.txt alphabetically
This is important because uniq only works on consecutive duplicate lines

- `uniq -u` Filters out all lines that appear more than once and shows only the ones that appear exactly once