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
# Background Processes
~~~
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!
UID          PID STAT CMD
root          82 S+   bash /challenge/run
root          84 R+   ps -o user=UID,pid,stat,cmd
I don't see a second me!
To pass this level, you need to suspend me, resume the suspended process in the
background, and then launch a new version of me! You can background me with
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &
Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!
UID          PID STAT CMD
root          82 S    bash /challenge/run
root          92 S    sleep 6h
root          93 S+   bash /challenge/run
root          95 R+   ps -o user=UID,pid,stat,cmd
Yay, I found another version of me running in the background! Here is the flag:
pwn.college{MwmErYAYB9EJxShmj9zYsvpXuf7.ddDN4QDL2kjN0czW}
~~~
# Foregrounding Processes 
~~~
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &
Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.
hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!
pwn.college{kYuXTh68ekyJUGLKMmj2uoLN-it.dhDN4QDL2kjN0czW}
~~~
# Starting Background Processes

~~~
hacker@processes~starting-backgrounded-processes:~$ fg
sleep 84
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[2] 99
Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...
Anyways! Here is your flag!
pwn.college{8kb2aHxmjtuon1CpATl-Pycv1qo.dlDN4QDL2kjN0czW}
~~~
# Process Exit Codes
A typical command that succeeds returns value 0 but the command that fails typically returns any value except 0.  
~~~
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ $?
ssh-entrypoint: 248: command not found
hacker@processes~process-exit-codes:~$ /challenge/submit-code 248
CORRECT! Here is your flag:
pwn.college{QMf3HUIzx7jb8Vj-ND4DZu_L3Mr.dljN4UDL2kjN0czW}
~~~

























