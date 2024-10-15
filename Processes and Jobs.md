# Listing Processes
In this challenge we learned about the command ps which just lists the processes running in your terminal. -e is for every process anf -f is for full format you can combine these arguments for -ef.
~~~
hacker@processes~listing-processes:/challenge$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 01:14 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /ru
root           7       1  0 01:14 ?        00:00:00 /run/dojo/bin/sleep 6h
root          68       1  0 01:14 ?        00:00:00 /challenge/24365-run-2874
root          72      68  0 01:14 ?        00:00:00 sleep 6h
hacker        73       0  0 01:15 pts/0    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker        93      73  0 01:16 pts/0    00:00:00 ps -ef
hacker@processes~listing-processes:/challenge$ /challenge/24365-run-2874
Yahaha, you found me! Here is your flag:
pwn.college{cjyvzGf6POOjiD1-VAaVMEawTOL.dhzM4QDL2kjN0czW}
~~~
# Killing Arguments
We can also terminate program using the kill command.  
We use kill to terminate programs by passing the process identifier as the argument.
~~~
hacker@processes~killing-processes:~$ ps -ef | grep dont_run
hacker        73      71  0 01:29 ?        00:00:00 /challenge/dont_run
hacker       110      92  0 01:30 pts/1    00:00:00 grep --color=auto dont_run
hacker@processes~killing-processes:~$ kill 0
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{QCtGSveHEgQyk9auX0zolhnJ96T.dJDN4QDL2kjN0czW}
~~~
# Interrupting Processes
~~~
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{0UCsx5JPfdrR6BIFJ9kKo5uwv_B.dNDN4QDL2kjN0czW}
~~~
# Suspending Processes
To suspend commands we use `ctrl+z`.
~~~
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!
UID          PID    PPID  C STIME TTY          TIME CMD
root          82      65  0 01:46 pts/0    00:00:00 bash /challenge/run
root          84      82  0 01:46 pts/0    00:00:00 ps -f
I don't see a second me!
To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!
UID          PID    PPID  C STIME TTY          TIME CMD
root          82      65  0 01:46 pts/0    00:00:00 bash /challenge/run
root         102      90  0 01:47 pts/0    00:00:00 bash /challenge/run
root         104     102  0 01:47 pts/0    00:00:00 ps -f
Yay, I found another version of me! Here is the flag:
pwn.college{YkyBLJmwxuPguqL5XLCQG2U-72N.dVDN4QDL2kjN0czW}
~~~
# Resuming Commands
When we suspend a program er need to resume it at some point. That's why we use fg command.
~~~
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{gaEZB5YEbbnHisewnf0LKk4rluh.dZDN4QDL2kjN0czW}
~~~


