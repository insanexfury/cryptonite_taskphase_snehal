# Redirecting Output
 This character is used to redirect stdout to files.
 ~~~
 hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{AKYpoCKUM6qFeNHuTeJnR_9h0ZP.dRjN1QDL2kjN0czW}
~~~
# Redirecting More Output
In this challenge I learned that `>(redirecting)` works for all commands not just the echo command.
~~~
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag
[HYPE] ONWARDS TO GREATNESS!
[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.
[TEST] You should have redirected my stdout to a file called myflag. Checking...
[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag
[FLAG] Here is your flag:
[FLAG] pwn.college{ge1LjwBSxxDC0FfUstG01V8ixvw.dVjN1QDL2kjN0czW}
~~~
# Appending Outputs
We can use >> to redirect input in append mode insted >.  
Using these redirection is a common way to save of some command results for later analysis. 
~~~
hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag
[HYPE] ONWARDS TO GREATNESS!
[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!
[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...
[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.
[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ cat /home/hacker/the-flag
 |
\|/ This is the first half:
 v
pwn.college{4DE2JS-ka8KTJtzOYbziCCrbPuX.ddDM5QDL2kjN0czW}                           ^
     that is the second half /|\
                              |
~~~
# Redirecting Errors
In this challenge we had to first redirect /challenge/run to myflag file using > then redirect standard file to the file instructions.
~~~
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{IjJnhGKZKuVvd229Fk_6u-Wfqjy.ddjN1QDL2kjN0czW}
~~~
# Redirecting Input
In this challenge I learned that we can not only redirect ouputs from commands using > but also redirect input in them using <.
~~~
hacker@piping~redirecting-input:~$ echo COLLEGE > pwn
hacker@piping~redirecting-input:~$ /challenge/run
You have not redirected anything to my standard input. Please do so, using '<'.
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{Y9GZVcvqsZKdFRSvd23AfVh7ecp.dBzN1QDL2kjN0czW}
~~~
# Grepping Stored Values
In this challenge first I needed to redirect the output of /challenge/run command to /tmp/data.txt file then grep the file with argument pwn(pwn because the flag alway starts with pwn) to find the flag.
~~~
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt
[HYPE] ONWARDS TO GREATNESS!
[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.
[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...
[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.
[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep pwn /tmp/data.txt
pwns
pwn
pwning
pwned
pwn.college{YfCXwwuXgw7g06RFUbDSaDDG8LY.dhTM4QDL2kjN0czW}
~~~
# Grepping Live Outputs
In this level I understood the `|` pipe operator, how it works.  
The standard output of the command to the left will be connected to the standard input of the command to the right of the pipe.
~~~
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt
[HYPE] ONWARDS TO GREATNESS!
[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.
[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!
[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.
[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwning
pwn.college{c2Kop2hrhVm6lCj1u8-ou03Vdh0.dlTM4QDL2kjN0czW}
~~~
# Grepping errors
~~~
hacker@piping~grepping-errors:~$  /challenge/run 2>&1 | grep "pwn"
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt
[HYPE] ONWARDS TO GREATNESS!
[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.
[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!
[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.
[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{IFKPnhvYdUmGPBgK4UFRMwzzOTL.dVDM5QDL2kjN0czW}
~~~
# Duplicating the Piped data with tee 
To want to see the data that flows between your commands to debug unintended errors we use the `tee` command.  
The `tee` command duplicates data to any no. of files provided to the command.

~~~
hacker@piping~duplicating-piped-data-with-tee:~$  /challenge/pwn | tee pan | /challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat pan
Usage: /challenge/pwn --secret [SECRET_ARG]
hacker@piping~duplicating-piped-data-with-tee:~$  /challenge/pwn --secret Uck4F5QZ | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{Uck4F5QZxKw71xBxxZjUNcKNgKV.dFjM5QDL2kjN0czW}
~~~
# Writing to Multiple Programs
In this challenge the `/challenge/hack` provides the output which is then directed to `/challenge/the` and `/challenge/planet`.  
`tee >` here makes a duplicate of `/challenge/hack`'s output and  sends a copy to /challenge/the.  
The orignal oupt goes to /challenge/planet.
~~~
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee > (/challenge/the) | /challenge/planet
Congratulations, you have duplicated data into the input of two programs! Here
is your flag:
pwn.college{gIRGjPHJTO9sprkW-gg9gCq2bfb.dBDO0UDL2kjN0czW}
~~~
# Split-Piping stderr and stdout
In this challenge I am just supposed to generate output from `/challenge/hack` then redirect its std output to `/challenge/planet` with the use of `> >()` and the final step to redirect the std error to `/challenge/the` with the use of `2> >()` .
~~~
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack > >( /challenge/planet ) 2> >( /challenge/the )
Congratulations, you have learned a redirection technique that even experts
struggle with! Here is your flag:
pwn.college{caMwP5WmvJVf7efqvrDULeBBlfz.dFDNwYDL2kjN0czW}
~~~
