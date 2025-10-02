# Level 9

## Explanation

The password is stored in the file data.txt in one of the few human-readable strings preceded ‘=’ characters

## Solution
<pre>
bandit9@bandit:~$ strings data.txt | grep "="
========== theg
VQ=97
[m=K1x
/i8D2[U?=
========== password
LU=W
========== is
=v$,
h{=,rw_c
=}%q
=D!7
YU=<
5=fq
vJ=ho
========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
=AdD
</pre>

- `strings data.txt` this extracts all human-readable text from the file 
- `grep '='` this filters the output and shows only the lines that contain an equal sign 