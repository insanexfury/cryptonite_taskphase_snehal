# The Root
Learned about absolute paths.
~~~bash
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{AxXR9ME-eIc7IDgiT1pftwrggIU.dhzN5QDL2kjN0czW}
~~~
# Program and absolute paths

~~~bash
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{s-DFKnGHMd7vRlc53F8JmLxJzlw.dVDN1QDL2kjN0czW}
~~~
# Position Thy Self
In this question I had problem looking for the correct directory.
~~~bash
hacker@paths~position-thy-self:~$ cd /
hacker@paths~position-thy-self:/$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{AbL-loXpzPRku7SrTTbmwxfwOTP.dZDN1QDL2kjN0czW}
~~~
# Position elsewhere
In this question my thought process was very similar to last one.
~~~bash
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /proc/67/fd directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /proc/67/fd
hacker@paths~position-elsewhere:/proc/67/fd$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{4fwOJoDP8DdLDJ_SiiyZkRTph7z.ddDN1QDL2kjN0czW}
~~~
# Position yet Elsewhere

~~~bash
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /
hacker@paths~position-yet-elsewhere:/$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{gaQO1ivzK9ZzTSmNUJ4Jz0bXnoR.dhDN1QDL2kjN0czW}
~~~
# Implicit Relative Paths
I learned the difference between relative paths and absolute paths.
~~~bash
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{AstdzUnQMSaSP45LHie19OiZ_Rb.dlDN1QDL2kjN0czW}
~~~
# Explicit Relative Path
How to use relative paths in programs.
~~~bash
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{0B3Xk90MJHrv8nagthI1Fm7R7Z3.dBTN1QDL2kjN0czW}
~~~
# Implicit Relative Path

~~~bash
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ /run
ssh-entrypoint: /run: Is a directory
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{w66XnvmNzA4mn1fQRRaJyK1Rc1e.dFTN1QDL2kjN0czW}
~~~
# Home sweet Home

~~~bash
hacker@paths~home-sweet-home:~$ /challenge/run /~
The argument you provided is not under your home directory!
hacker@paths~home-sweet-home:~$ /challenge/run ~/~
Writing the file to /home/hacker/~!
... and reading it back to you:
pwn.college{INaTKfhb7jDTk0Pm7BKl_A2bkgK.dNzM4QDL2kjN0czW}
~~~

