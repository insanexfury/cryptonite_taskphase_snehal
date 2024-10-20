# Chaining with Semicolons
We can chain commands using semicolons.
~~~
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{EIV1hOMa3AcLmlEmj-R7qAFQfaz.dVTN4QDL2kjN0czW}
~~~
# Your First Shell Script 
We learnt to create a shell script ending with .sh suffix.
~~~
hacker@chaining~your-first-shell-script:~$ echo /challenge/pwn > x.sh
hacker@chaining~your-first-shell-script:~$ echo /challenge/college >> x.sh
hacker@chaining~your-first-shell-script:~$ cat x.sh
/challenge/pwn
/challenge/college
hacker@chaining~your-first-shell-script:~$ chmod +x x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{IXd6kAHBMsK78h1cHKAJQofCftQ.dFzN4QDL2kjN0czW}
~~~
# Redirecting Script Output
We can also redirect script output using piping.
~~~
hacker@chaining~redirecting-script-output:~$ echo /challenge/pwn > x.sh
hacker@chaining~redirecting-script-output:~$ echo /challenge/college >> x.sh
hacker@chaining~redirecting-script-output:~$ chmod +x x.sh
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{oAM51RzDPE-60VSeWCDt2thZBD9.dhTM5QDL2kjN0czW}
~~~
# Executable Shell Scripts 
We don't need the bash command to execute shell script file just by doing  
/home/hacker/script.sh  
~/script.sh  
./script.sh  
~~~
hacker@chaining~executable-shell-scripts:~$ echo /challenge/solve > c.sh
hacker@chaining~executable-shell-scripts:~$ chmod +x c.sh
hacker@chaining~executable-shell-scripts:~$ ./c.sh
Congratulations on your shell script execution! Your flag:
pwn.college{k2C4Yip-vwX4GZsgiE7mYQY96Cf.dRzNyUDL2kjN0czW}
~~~

























