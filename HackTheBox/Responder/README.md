```
Platform: HackThebox
Challenge: Responder
OS: Windows
Task: WinRM, Web, Network, Custom Applications, Protocols, XAMPP, SMB, Responder, PHP, Penetration Tester Level 1, Reconnaissance, Password Cracking, Hash Capture, Remote File Inclusion, Remote Code Execution
Tools Used: 
Author: Paul B.
```
TASK 1

When visiting the web service using the IP address, what is the domain that we are being redirected to?
```
unika.htb
```

TASK 2

Which scripting language is being used on the server to generate webpages?
```
PHP
```

TASK 3

What is the name of the URL parameter which is used to load different language versions of the webpage?
```
page
```

TASK 4

Which of the following values for the `page` parameter would be an example of exploiting a Local File Include (LFI) vulnerability: "french.html", "//10.10.14.6/somefile", "../../../../../../../../windows/system32/drivers/etc/hosts", "minikatz.exe"
```
../../../../../../../../windows/system32/drivers/etc/hosts
```

TASK 5

Which of the following values for the `page` parameter would be an example of exploiting a Remote File Include (RFI) vulnerability: "french.html", "//10.10.14.6/somefile", "../../../../../../../../windows/system32/drivers/etc/hosts", "minikatz.exe"
```
//10.10.14.6/somefile
```

TASK 6

What does NTLM stand for?
```
New Technology Lan Manager
```

TASK 7

Which flag do we use in the Responder utility to specify the network interface?
```
-i
```

TASK 8

There are several tools that take a NetNTLMv2 challenge/response and try millions of passwords to see if any of them generate the same response. One such tool is often referred to as `john`, but the full name is what?.
```
john the ripper
```

TASK 9

What is the password for the administrator user?
```
```

TASK 10

We'll use a Windows service (i.e. running on the box) to remotely access the Responder machine using the password we recovered. What port TCP does it listen on?
```
```

SUBMIT FLAG

Submit root flag
```
```
