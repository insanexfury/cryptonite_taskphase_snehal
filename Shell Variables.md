# Printing Variables
In this challenge `/challenge/run` program will not print the flag but flag was stored in a variable `FLAG` which was to be accesed by echo $.
~~~
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{cWajg-XdIkLvxQmXwR-0iG1IY6v.ddTN1QDL2kjN0czW}
~~~
# Setting Variables
You can not only print values of a variale but can also set them using `=`.
~~~
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{g2I8lelxx9xo07MKpskwJSnJUOB.dlTN1QDL2kjN0czW}
~~~
# Multi Word Variable
To put spaces in a variable we need to quote it like `"pwn sauce"`. If you don't quote it wil treat the value after space as command.
~~~
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{wKGgUjdwXP330YORoVuhbnK4MeZ.dBjN1QDL2kjN0czW}
~~~
# Exporting Variables
In this challenge we had to store variable COLLEGE in PWN exported and PWN variable in COLLEGE not exported and run program /challenge/run.
~~~
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great
job! Here is your flag:
pwn.college{M53aohIYxnD5lBgBoixanZ3A7kR.dJjN1QDL2kjN0czW}
~~~
# Printing Exported Variables
This level we learned a new command to print out evey exported variable in the shell `env`.
~~~
hacker@variables~printing-exported-variables:~$ env $FLAG
env: ‘pwn.college{ML8QRyJzRCvCkTOBwgDWff-fJuH.dhTN1QDL2kjN0czW}’
~~~
# Storing Command Outputs
Yoy can also store the output of commands in a variable easily.
~~~
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{wFpRnxg1-KloQnb0xIYlaYCh9jY.dVzN0UDL2kjN0czW}
~~~
# Reading Input
We can also read inputs to variable using `read` command.
~~~
hacker@variables~reading-input:~$ read PWN
COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{00oZBL27e90DH-A6sRbE0U7NqIk.dhzN1QDL2kjN0czW}
~~~
# Reading Files
we can use read command to store output of commands or files in variables.
~~~
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{g0q_SCHlVkIytWuMnedPuE4KHDx.dBjM4QDL2kjN0czW}
~~~



