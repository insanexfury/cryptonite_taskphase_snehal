# The PATH Variable
~~~
hacker@path~the-path-variable:~$ PATH="rm"
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: command not found
The flag is still there! I might as well give it to you!
pwn.college{UlfqZXuU_7LMvvwqpjtigFsBFoy.dZzNwUDL2kjN0czW}
~~~
# Setting Paths
~~~
hacker@path~setting-path:~$ PATH="/challenge/more_commands/"
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{wTCwYfjTZ0i3ea5VQ1ml2d2s87Z.dVzNyUDL2kjN0czW}
~~~
# Adding Commands 
~~~
hacker@path~adding-commands:~$ echo "/usr/bin/cat /flag" > win
hacker@path~adding-commands:~$ ./win
/usr/bin/cat: /flag: Permission denied
hacker@path~adding-commands:~$ chmod +x win
hacker@path~adding-commands:~$ PATH='~'
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{A8oJE63WDaMdRJjC1_InKdGq0rO.dZzNyUDL2kjN0czW}
~~~

