```
Platform: HackThebox
Challenge: Meow
OS: Linux
Task: Telnet, Penetration Tester Level 1, Network, Protocols, Reconnaissance, Weak Credentials, Misconfiguration
Tools Used: Nmap, Telnet
Author: Paul B.
```

### Task 1
What does the acronym VM stand for?
```
Virtual Machine
```
### Task 2
What tool do we use to interact with the operating system in order to issue commands via the command line, such as the one to start our VPN connection? It's also known as a console or shell.
```
Terminal
```
### Task 3
What service do we use to form our VPN connection into HTB labs?
```
openvpn
```
### Task 4
What is the abbreviated name for a 'tunnel interface' in the output of your VPN boot-up sequence output?
```
tun
```
### Task 5
What tool do we use to test our connection to the target with an ICMP echo request?
```
ping
```
### Task 6
What is the name of the most common tool for finding open ports on a target?
```
nmap
```
### Task 7
What service do we identify on port 23/tcp during our scans?
```
Telnet
```
### Task 8
What username is able to log into the target over telnet with a blank password?
```
root
```


### Scanning
#### Nmap output
```
Starting Nmap 7.80 ( https://nmap.org ) at 2023-01-03 22:00 IST
Nmap scan report for 10.129.173.122
Host is up (2.9s latency).
Not shown: 999 closed ports
PORT   STATE SERVICE VERSION
23/tcp open  telnet  Linux telnetd
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 55.39 seconds
```

### Gaining Access
Connect via telent using command
```
telnet <target ip address>
```


![HTB - Meow - Telnet.png](:/b16d40c358b846a9b6133013c8216eaa)

### Root Flag
```
b40abdfe23665f766f9c61ecba8a4c19
```
