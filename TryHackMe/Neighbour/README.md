```
Platform: TryHackMe
Challenge: Neighbour
Task: Web, IDOR
Author: Paul B.
```

In the login page, we can see the message that if we don't have an account means to press `Ctrl-U` which opens up the source code. In the source code, we can find the credential for guest user as `guest:guest`

Once logged in, We are presented with a simple webpage containing a button to logout. We don't find anything useful in the source code too but if we look at the URL closely. We can see a paramter called `user` which is set to `guest`. Let's change the value to `admin` and see the response

Nice and Easy, we can access admin page and got our flag.

### Answer the questions below
Find the flag on your neighbor's logged in page!
```
flag{66be95c478473d91a5358f2440c7af1f}
```
