```
Platform: TryHackMe
Challenge: Epoch
Task: Command Injection
OS:
Tools Used:
Author: Paul B.
```

### What is Epoch
Epoch is the starting point (date and time) from which they measure the system time. Epoch is the zero point for a computer’s time i.e., it represents the 00 hours, 00 minutes and 00 seconds. Different operating systems have different epoch times. For instance, in UNIX and POSIX based operating systems, the epoch time is 00:00:00 UTC, Thursday 1st January 1970. Computers based on UNIX measure time by counting the number of seconds that passed (minus the leap seconds) from this point. Hence, this Epoch time is also known as Unix Epoch Time (or simple Epoch Time, Unix Time, POSIX Time). Developers of Unix Ken Thompson and Dennis Ritchie are also responsible for setting the epoch date and time as 1st January, 1970 and 00:00:00.

### Tasks
Navigating to the website, we are presented with simple epoch converter

`printenv` command – Print all or part of environment.


### Answer the questions below
Find the flag in this vulnerable web application!
```
flag{7da6c7debd40bd611560c13d8149b647}
```
