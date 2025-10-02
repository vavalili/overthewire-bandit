# Level 12

## Explanation 

The file `data.txt` is a hexdump of a file that has been compressed multiple times.

## Solution
<pre>
bandit12@bandit:~$ cd /tmp
bandit12@bandit:/tmp$ mkdir level12directory
bandit12@bandit:/tmp$ cp ~/data.txt /tmp/level12directory
bandit12@bandit:/tmp$ cd level12directory
bandit12@bandit:/tmp/level12directory$ ls
data.txt
bandit12@bandit:/tmp/level12directory$ xxd -r data.txt > data.bin
bandit12@bandit:/tmp/level12directory$ ls
data.bin  data.txt
bandit12@bandit:/tmp/level12directory$ file data.bin
data.bin: gzip compressed data, was "data2.bin", last modified: Fri Aug 15 13:15:53 2025, max compression, from Unix, original size modulo 2^32 584
bandit12@bandit:/tmp/level12directory$ mv data.bin data.gz
bandit12@bandit:/tmp/level12directory$ gunzip data.gz
bandit12@bandit:/tmp/level12directory$ ls
data  data.txt
bandit12@bandit:/tmp/level12directory$ file data
data: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/level12directory$ bzip2 -d data
bzip2: Can't guess original name for data -- using data.out
bandit12@bandit:/tmp/level12directory$ ls
data.out  data.txt
bandit12@bandit:/tmp/level12directory$ bzip2 -d data.out
bzip2: Can't guess original name for data.out -- using data.out.out
bzip2: data.out is not a bzip2 file.
bandit12@bandit:/tmp/level12directory$ file data.out
data.out: gzip compressed data, was "data4.bin", last modified: Fri Aug 15 13:15:53 2025, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/level12directory$ ls
data.out  data.txt
bandit12@bandit:/tmp/level12directory$ mv data.out data.gz
bandit12@bandit:/tmp/level12directory$ gunzip data.gz
bandit12@bandit:/tmp/level12directory$ ls
data  data.txt
bandit12@bandit:/tmp/level12directory$ file data
data: POSIX tar archive (GNU)
bandit12@bandit:/tmp/level12directory$ tar mv data data.tar
tar: You must specify one of the '-Acdtrux', '--delete' or '--test-label' options
Try 'tar --help' or 'tar --usage' for more information.
bandit12@bandit:/tmp/level12directory$ mv data data.tar
bandit12@bandit:/tmp/level12directory$ tar -xf data.tar
bandit12@bandit:/tmp/level12directory$ ls
data5.bin  data.tar  data.txt
bandit12@bandit:/tmp/level12directory$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/level12directory$ mv data5.bin data5.tar
bandit12@bandit:/tmp/level12directory$ tar -xf data5.tar
bandit12@bandit:/tmp/level12directory$ ls
data5.tar  data6.bin  data.tar  data.txt
bandit12@bandit:/tmp/level12directory$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/level12directory$ bzip2 -d data6.bin
bzip2: Can't guess original name for data6.bin -- using data6.bin.out
bandit12@bandit:/tmp/level12directory$ ls
data5.tar  data6.bin.out  data.tar  data.txt
bandit12@bandit:/tmp/level12directory$ file data6.bin.out
data6.bin.out: POSIX tar archive (GNU)
bandit12@bandit:/tmp/level12directory$ mv data6.bin.out data6.tar
bandit12@bandit:/tmp/level12directory$ tar -xf data6.tar
bandit12@bandit:/tmp/level12directory$ ls
data5.tar  data6.tar  data8.bin  data.tar  data.txt
bandit12@bandit:/tmp/level12directory$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Fri Aug 15 13:15:53 2025, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/level12directory$ mv data8.bin data8.gz
bandit12@bandit:/tmp/level12directory$ gunzip data8.gz
bandit12@bandit:/tmp/level12directory$ ls
data5.tar  data6.tar  data8  data.tar  data.txt
bandit12@bandit:/tmp/level12directory$ file data8
data8: ASCII text
bandit12@bandit:/tmp/level12directory$ cat data8
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
</pre>


- <pre> mkdir level12directory 
cp ~/data.txt /tmp/level12directory </pre> 
created a safe working directory in /tmp to avoid cluttering the home folder
- `xxd -r data.txt > data.bin` used xxd -r to reverse the hexdump and recreate the original binary
- file used to inspect each layer and applied the correct decompression tool based on the format:

gzip → `gunzip`

bzip2 → `bzip2 -d`

tar archive → `tar -xf`

repeate this process several times, renaming files when necessary to match expected extensions (e.g. .gz, .tar), until you reached the final file.
