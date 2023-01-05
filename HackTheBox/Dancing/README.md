```
Platform: HackThebox
Challenge: Dancing
OS: Windows
Task: Network ,Protocols, SMB, Penetration Tester Level 1, Reconnaissance, Anonymous/Guest Access
Tools Used: Windows, smbclient
Author: Paul B.
```

### Scanning
Nmap output:
```
Starting Nmap 7.80 ( https://nmap.org ) at 2023-01-04 20:54 IST
Nmap scan report for 10.129.158.119
Host is up (1.8s latency).
Not shown: 997 closed ports
PORT    STATE SERVICE       VERSION
135/tcp open  msrpc         Microsoft Windows RPC
139/tcp open  netbios-ssn   Microsoft Windows netbios-ssn
445/tcp open  microsoft-ds?
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
|_clock-skew: 4h00m00s
| smb2-security-mode: 
|   2.02: 
|_    Message signing enabled but not required
| smb2-time: 
|   date: 2023-01-04T19:24:32
|_  start_date: N/A

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 34.85 seconds

```
### SMB Enumeration
SMB list shares:
`smbclient -L <target ip>`
```
	Sharename       Type      Comment
	---------       ----      -------
	ADMIN$          Disk      Remote Admin
	C$              Disk      Default share
	IPC$            IPC       Remote IPC
	WorkShares      Disk 
```

SMB enumerate share
`smbclient \\\\<target ip>\\WorkShares`


TASK 1
What does the 3-letter acronym SMB stand for?
```
server message block
```

TASK 2
What port does SMB use to operate at?
```
445
```

TASK 3
What is the service name for port 445 that came up in our Nmap scan?
```
microsoft-ds
```

TASK 4
What is the 'flag' or 'switch' we can use with the SMB tool to 'list' the contents of the share?
```
-l
```

TASK 5
How many shares are there on Dancing?
```
4
```

TASK 6
What is the name of the share we are able to access in the end with a blank password?
```
WorkShares
```

TASK 7
What is the command we can use within the SMB shell to download the files we find?
```
get
```

SUBMIT root flag
```
5f61c10dffbc77a704d76016a22f1664
```
