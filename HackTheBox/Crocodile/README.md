```
Platform: HackThebox
Challenge: Crocodile
OS: 
Task: Web, Network, Custom Applications, Protocols, Apache, FTP, Penetration Tester Level 1, Reconnaissance, Web Site Structure Discovery, Clear Text Credentials, Anonymous/Guest Access
Tools Used: 
Author: Paul B.
```

### Scanning
Nmap output
```
Starting Nmap 7.80 ( https://nmap.org ) at 2023-01-10 21:05 IST
Nmap scan report for 10.129.22.116
Host is up (1.1s latency).
Not shown: 998 closed ports
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
| -rw-r--r--    1 ftp      ftp            33 Jun 08  2021 allowed.userlist
|_-rw-r--r--    1 ftp      ftp            62 Apr 20  2021 allowed.userlist.passwd
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to ::ffff:10.10.16.164
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 2
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
80/tcp open  http    Apache httpd 2.4.41 ((Ubuntu))
|_http-server-header: Apache/2.4.41 (Ubuntu)
|_http-title: Smash - Bootstrap Business Template
Service Info: OS: Unix

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 21.83 seconds
```

TASK 1

What nmap scanning switch employs the use of default scripts during a scan?
```
-sC
```

TASK 2

What service version is found to be running on port 21?
```
vsftpd 3.0.3
```

TASK 3

What FTP code is returned to us for the "Anonymous FTP login allowed" message?
```
230
```

TASK 4

What command can we use to download the files we find on the FTP server?
```
get
```

TASK 5

What is one of the higher-privilege sounding usernames in the list we retrieved?
```
admin
```

TASK 6

What version of Apache HTTP Server is running on the target host?
```
2.4.41
```

TASK 7

What is the name of a handy web site analysis plug-in we can install in our browser?
```
wappalyzer
```

TASK 8

What switch can we use with gobuster to specify we are looking for specific filetypes?
```
-x
```

TASK 9

What file have we found that can provide us a foothold on the target?
```
login.php
```

SUBMIT FLAG

Submit root flag
```
c7110277ac44d78b6a9fff2232434d16
```
