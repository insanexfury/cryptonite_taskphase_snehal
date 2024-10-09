# Learning from Documentation
The program for this challenge was /challenge/challenge and I had to properly use the argument --giveflag for the flag.
~~~
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{gtU1-trdE2XmDPldlRD2VkhVDw6.dRjM5QDL2kjN0czW}
~~~
# Learning Complex usage

~~~
hacker@man~learning-complex-usage:~$ ls
 COLLEGE   COLLENGE   FD_CLOEXEC   f   instructions   myflag   not-the-flag   r   stdout   the-flag  '~'
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile myflag
Correct argument! Here is the myflag file:
[FLAG] Here is your flag:
[FLAG] pwn.college{IjJnhGKZKuVvd229Fk_6u-Wfqjy.ddjN1QDL2kjN0czW}
~~~
# Reading Manuals
This level introduces the man command.
~~~
hacker@man~reading-manuals:~$ man challenge
DESCRIPTION
       Output the flag when called with the right arguments.
       --fortune
              read a fortune
       --version
              output version information and exit
       --wubwbd NUM
              print the flag if NUM is 264
hacker@man~reading-manuals:~$ /challenge/challenge --wubwbd 264
Correct usage! Your flag: pwn.college{wCTuTYDb2wAMLbLdolfZS6tLGch.dRTM4QDL2kjN0czW}
~~~
# Searching Manuals
Commands like / to search the man page ,? command to search the man pages backwardly, and n which goes to the next result.
~~~
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$
hacker@man~searching-manuals:~$ /challenge/challenge  --bqag
Initializing...
Correct usage! Your flag: pwn.college{8Z5pW1y-QEqmkRhaurcjMrv4ODc.dVTM4QDL2kjN0czW}
~~~
# Searching for manuals
This challenge was tricky it hid the manpage for the challenge by hiding its name.  
We were to read the man pages by `man man` command it teaches advance usage of man command itself.  

# Helpful Programs
when programs do not have a man page we might find something usefuls by invoking the argument `--help` or `-h`.
~~~
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 477
hacker@man~helpful-programs:~$ /challenge/challenge -g 477
Correct usage! Your flag: pwn.college{4LCulJDkM-7DQGPi7vYPrGX6jg6.ddjM4QDL2kjN0czW}
~~~
#   Help for Builtins

~~~
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "AYDCTINo".
hacker@man~help-for-builtins:~$ challenge --secret AYDCTINo
Correct! Here is your flag!
pwn.college{AYDCTINobPZha69dPrzN3xdBw_8.dRTM5QDL2kjN0czW}
~~~





