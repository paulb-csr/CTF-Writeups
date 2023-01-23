```
Platform: TryHackMe
Challenge: Epoch
Task: Command Injection
OS: Linux
Tools Used: None
Author: Paul B.
```

### What is Epoch
Epoch is the starting point (date and time) from which they measure the system time. Epoch is the zero point for a computer’s time i.e., it represents the 00 hours, 00 minutes and 00 seconds. Different operating systems have different epoch times. For instance, in UNIX and POSIX based operating systems, the epoch time is 00:00:00 UTC, Thursday 1st January 1970. Computers based on UNIX measure time by counting the number of seconds that passed (minus the leap seconds) from this point. Hence, this Epoch time is also known as Unix Epoch Time (or simple Epoch Time, Unix Time, POSIX Time).

### Tasks
Navigating to the website, we are presented with simple Epoch to UTC converter
![Epoch Converter](https://raw.githubusercontent.com/paulb-csr/CTF-Writeups/main/TryHackMe/Epoch/THM%20-%20Epoch%20Website.png)

Let's try to convert a random value
![Conversion](https://raw.githubusercontent.com/paulb-csr/CTF-Writeups/main/TryHackMe/Epoch/THM%20-%20Epoch%20Website%20convert%20example.png)

Let's try with different input and check how application behaves, Entering `ls` to check whether we are presented with directory listing
![ls error](https://raw.githubusercontent.com/paulb-csr/CTF-Writeups/main/TryHackMe/Epoch/THM%20-%20Epoch%20Website%20Error.png)

We are getting an error. Let's try [linux command chaining](https://www.howtogeek.com/269509/how-to-run-two-or-more-terminal-commands-at-once-in-linux/) using `&` symbol
![Command chaining](https://raw.githubusercontent.com/paulb-csr/CTF-Writeups/main/TryHackMe/Epoch/THM%20-%20Epoch%20Website%20concatenate%20commands.png)

Great! We can see the output of `ls` command. Based on the Hint from TryHackMe it is mentioned that `The developer likes to store data in environment variables, can you find anything of interest there?`. 

In linux, we can print environement variable using the command `printenv` command – Print all or part of environment
![Epoch flag](https://raw.githubusercontent.com/paulb-csr/CTF-Writeups/main/TryHackMe/Epoch/THM%20-%20Epoch%20Flag.png)

### Answer the questions below
Find the flag in this vulnerable web application!
```
flag{7da6c7debd40bd611560c13d8149b647}
```
