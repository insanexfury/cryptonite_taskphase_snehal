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

