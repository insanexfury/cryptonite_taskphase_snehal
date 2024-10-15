# Changing File Ownership
This can be done by using command `chown`. But only the root user can use this.  
In this challenge we had to get ownership of `/flag` file.
~~~
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{w0scFzWFlclJ1Tqjsw5amybegfR.dFTM2QDL2kjN0czW}
~~~
# Groups and Files
Just like the last challenge we had to change ownership in this one we have to change groups to access the `/flag` file.  
To change group we use `chgrp` command.
~~~
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{USargFntW07t5K9y-AxFu0RXnbW.dFzNyUDL2kjN0czW}
~~~
