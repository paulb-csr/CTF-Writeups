```
Platform: HackThebox
Challenge: Redeemer
OS: Windows
Task: Redis, Penetration Tester Level 1, Vulnerability Assessment, Databases, Reconnaissance, Anonymous/Guest Access
Tools Used: Nmap, redis-cli
Author: Paul B.
```

### Scanning
Nmap output:
```
Starting Nmap 7.80 ( https://nmap.org ) at 2023-01-04 21:58 IST
Initiating Parallel DNS resolution of 1 host. at 21:58
Completed Parallel DNS resolution of 1 host. at 21:58, 0.02s elapsed
Initiating Connect Scan at 21:58
Scanning 10.129.151.14 [9000 ports]
Discovered open port 6379/tcp on 10.129.151.14
Completed Connect Scan at 22:11, 816.10s elapsed (9000 total ports)
Nmap scan report for 10.129.151.14
Host is up, received user-set (0.22s latency).
Scanned at 2023-01-04 21:58:13 IST for 816s
Not shown: 8205 closed ports, 794 filtered ports
Reason: 8205 conn-refused and 794 no-responses
PORT     STATE SERVICE REASON
6379/tcp open  redis   syn-ack

Read data files from: /usr/bin/../share/nmap
Nmap done: 1 IP address (1 host up) scanned in 816.23 seconds
```

Redis service enumeration
```
# Nmap 7.80 scan initiated Wed Jan  4 22:22:06 2023 as: nmap -sC -sV -p 6379 -oN redis-service-enum.txt 10.129.151.14
Nmap scan report for 10.129.151.14
Host is up (0.18s latency).

PORT     STATE SERVICE VERSION
6379/tcp open  redis   Redis key-value store 5.0.7

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Wed Jan  4 22:22:15 2023 -- 1 IP address (1 host up) scanned in 8.97 seconds
```

### Redis setup
Install redis-server `sudo apt install redis-server`

### Redis enumeration
Connect to redis database `redis-cli -h <target ip> -p 6379`

### TASK 1
Which TCP port is open on the machine?
```
6379
```

### TASK 2
Which service is running on the port that is open on the machine?
```
redis
```

### TASK 3
What type of database is Redis? Choose from the following options: (i) In-memory Database, (ii) Traditional Database
```
In-memory Database
```

### TASK 4
Which command-line utility is used to interact with the Redis server? Enter the program name you would enter into the terminal without any arguments.
```
redis-cli
```

### TASK 5
Which flag is used with the Redis command-line utility to specify the hostname?
```
-h
```

### TASK 6
Once connected to a Redis server, which command is used to obtain the information and statistics about the Redis server?
```
info
```

### TASK 7
What is the version of the Redis server being used on the target machine?
```
5.0.7
```

### TASK 8
Which command is used to select the desired database in Redis?
```
select
```

### TASK 9
How many keys are present inside the database with index 0?
```
4
```

### TASK 10
Which command is used to obtain all the keys in a database?
```
keys *
```

### SUBMIT ROOT FLAG
```
03e1d2b376c37ab3f5319922053953eb
```
