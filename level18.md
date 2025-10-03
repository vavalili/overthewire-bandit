# Level 18

## Explanation

The  password for Level 19 is stored in a file called readme in Bandit 18’s home directory but when you try to log in to Bandit 18 using SSH, you get logged out immediately. That’s because someone edited the .bashrc file to force a logout as soon as the shell starts

## Solution
<pre>
pc>ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

backend: gibson-0
bandit18@bandit.labs.overthewire.org's password:
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
</pre>

`ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"` This tells SSH  to just run cat readme and exit avoiding .bashrc entirely
