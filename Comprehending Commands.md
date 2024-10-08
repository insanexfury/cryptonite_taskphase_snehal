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
pwn.college{4cCWvLiy2nn6Imw5IxqwZWDaujq.dBTN4QDL2kjN0czW}
~~~
# An eepic filesystem Quest



