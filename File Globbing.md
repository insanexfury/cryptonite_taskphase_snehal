# Matching with *
The first glob that I learned was *.  
When the * encounters character in any argument it tries to replace that argument with any file of that pattern.  
In tnis challenge I had to cd into /challenge but had to use globbing to keep the argument at most 4 characters only.
~~~
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{4bIB5m6JbzyJ2x6frmzXmbbBO0b.dFjM4QDL2kjN0czW}
~~~
# Matching with ?
the ? glob acts like the * but only matches one character.
~~~
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{EnmiVtyOkvUI_i5jbJ6S8p5GrCr.dJjM4QDL2kjN0czW}
~~~
# Matching with []
The square brackets are essentially a limited form of ?.  
[] is a subset of potential characters specified within the brackets.
~~~
hacker@globbing~matching-with-:~$ /challenge/files
ssh-entrypoint: /challenge/files: Is a directory
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ ls
file_a  file_c  file_e  file_g  file_i  file_k  file_m  file_o  file_q  file_s  file_u  file_w  file_y
file_b  file_d  file_f  file_h  file_j  file_l  file_n  file_p  file_r  file_t  file_v  file_x  file_z
hacker@globbing~matching-with-:/challenge/files$ cat file_[absh]
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[absh]
You got it! Here is your flag!
pwn.college{AY0zbmO9SklfV_j_qJqyL_rgwS_.dNjM4QDL2kjN0czW}
~~~





