```
Platform: HackThebox
Challenge: Fawn
OS: Unix
Task: Penetration Tester Level 1, FTP, Network Protocols, Reconnaissance, Anonymous/Guest Access
Tools Used: Nmap, ftp
Author: Paul B.
```
### TASK 1
What does the 3-letter acronym FTP stand for?
```
file transfer protocol
```

### TASK 2
Which port does the FTP service listen on usually?
```
21
```

### TASK 3
What acronym is used for the secure version of FTP?
```
sftp
```

### TASK 4
What is the command we can use to send an ICMP echo request to test our connection to the target?
```
ping
```

### TASK 5
From your scans, what version is FTP running on the target?
```
vsftpd 3.0.3
```

### TASK 6
From your scans, what OS type is running on the target?
```
Unix
```

### TASK 7
What is the command we need to run in order to display the 'ftp' client help menu?
```
ftp -h
```

### TASK 8
What is username that is used over FTP when you want to log in without having an account?
```
anonymous
```

### TASK 9
What is the response code we get for the FTP message 'Login successful'?
```
230
```

### TASK 10
There are a couple of commands we can use to list the files and directories available on the FTP server. One is dir. What is the other that is a common way to list files on a Linux system.
```
ls
```

### TASK 11
What is the command used to download the file we found on the FTP server?
```
get
```

### Reconnaissance
### Scanning
Nmap output:
```
# Nmap 7.80 scan initiated Tue Jan  3 22:26:33 2023 as: nmap -sS -sV -sC -oN nmap-scan.txt 10.129.92.81
Nmap scan report for 10.129.92.81
Host is up (0.82s latency).
Not shown: 999 closed ports
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_-rw-r--r--    1 0        0              32 Jun 04  2021 flag.txt
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to ::ffff:10.10.16.160
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 4
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
Service Info: OS: Unix

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Tue Jan  3 22:26:52 2023 -- 1 IP address (1 host up) scanned in 19.47 seconds
```

### SUBMIT root flag
```
035db21c881520061c53e0536e44f815paulb
```
