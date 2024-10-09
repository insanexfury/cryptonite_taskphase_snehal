# Cat: not the pet but the command
Learned about the cat command which reads out the content of files.
~~~bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{8N7R75zxoE1V0aStrDyaX0mq2o-.dFzN1QDL2kjN0czW}
~~~
# Catting Absolute Paths
Cat's argument can be specified to absolute paths.
~~~bash
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{c7uu_E59AT866OacNCPSIPXpJrn.dlTM5QDL2kjN0czW}
~~~
# More catting practice
~~~bash
hacker@commands~more-catting-practice:~$ cd
You used 'cd'! In this level, I don't allow you to change the working directory
--- you MUST chase pass 'cat' the absolute path of where I put it on the
filesystem (which is /lib/kernel/flag).
hacker@commands~more-catting-practice:~$ cat /lib/kernel/flag
pwn.college{41zK9Ym1_3dBResAS6OvWuhaQr8.dBjM5QDL2kjN0czW}
~~~
# Grepping for needle in haystack
New command learned grep which searches for specific string in lines of files.
~~~bash
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{gwQWp2ms0r9COVVTJLlSRKu2o1S.ddTM4QDL2kjN0czW}
~~~
# Listing files
ls is a command used to listing files in a directory.
~~~bash
hacker@commands~listing-files:~$ ls /challenge
10680-renamed-run-10295  DESCRIPTION.md
hacker@commands~listing-files:~$ ./10680-renamed-run-10295
ssh-entrypoint: ./10680-renamed-run-10295: No such file or directory
hacker@commands~listing-files:~$ /challenge/10680-renamed-run-10295
Yahaha, you found me! Here is your flag:
pwn.college{0TbrNW3ihHE0MObOVnvuzBad2lu.dhjM4QDL2kjN0czW}
~~~
# Touching Files
Touch is another one of the new commnds which I learned in this module,it creates files.
~~~bash
hacker@commands~touching-files:~$ touch /tmp/pwn
hacker@commands~touching-files:~$ touch /tmp/college
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
pwn.college{YOs7bq7BTDO55sHieirBdz7k3-z.dBzM4QDL2kjN0czW}
~~~
# removing files
Files are removed by the command rm.
~~~bash
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{YyLKmx7yWbtC0xkDUXHY4qK_d7w.dZTOwUDL2kjN0czW}
~~~
# Hidden Files
hidden files in a directory can be visible by just modifying the ls command, adding -a after it.(ls -a)
~~~bash
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.   .dockerenv             bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-140412502531835  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:/$ cat .flag-140412502531835
~~~
# An epic filesystem Quest
In this question I had problem in reading the file but without cd'ing into the directory.  
but after some attempts I figured what to do.
~~~bash
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{oplwIxhh_rnoXHT9DlJ3oaFpBjP.dljM4QDL2kjN0czW}
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/cycler-0.10.0.egg-info$
~~~
# Making directories
mkdir is the command used for making new directories. In this challenge I had to  create a /tmp/pwn directory and make a college file in it and then run /challenge/run.
~~~bash
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{AkgkKJOMFoxQaoS-L82dV7XWLWU.dFzM4QDL2kjN0czW}
~~~
# Finding files
In this challenge I had to search for for the correct /path/to/flag using the find and cat command.
 ~~~bash
hacker@commands~finding-files:~$ cat /usr/share/racket/pkgs/plot-lib/plot/flag
pwn.college{c87NNUb4oc6BLGLbwr93d1LXpzH.dJzM4QDL2kjN0czW}
~~~
# Linking Files
 In this level the flag is, as always, in /flag, but /challenge/catflag will instead read out /home/hacker/not-the-flag.I had to use the symlink to fool it into giving the flag.
~~~
hacker@commands~linking-files:~$ ln -sf /flag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{gwzx5QgybXfgVYEX0sp7JuS8pM9.dlTM1UDL2kjN0czW}
~~~






