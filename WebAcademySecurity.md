# Server-side vulnerabilities

## Path traversal

### Solution:
To get to the target file, i used this ```bash /image?filename=/../../../etc/passwd``` which i found using the inspect tool that files were being accessed in this manner and solved the challenge. 

### Learnings:
I learnt what Path traversal vulnerability was and how it can be exploited by attackers.

## Access control

### Solution:
For the first lab, i got the admin panel path by accessing the file robots.txt. For the second lab, i got the admin panel path by checking the script of the website using the inspect tool of the chrome. For the third lab, i created a new cookie named Admin and entered its value as true and refreshed the ```bash /admin``` page and got the access.For the fourth lab i got the user carlos' GUID by checking his post using the inspect tool and then in the ```bash /my-accounts``` page i entered his GUID to gain access of his page and got his API key.For the fifth lab, i login into the user acoount wiener and then changed the ```bash /my-accounts?id= ``` value to administrator and then got the access to admin panel and deleted the carlos user.

### Learnings:
I learnt how access control can be achieved by exploiting various vulnerabilities like Unprotected functinality, parameter-based methods. Also i learnt how vertical and horizontal privilege escalations can be achieved. 

## Authentication

### Solution:
For the first lab, i opened the lab in the bur suite browser and intercepted the http requests of user login. Then i highlighted the username entered and sent it to intruder and initiated a snipe attack using the set of usernames given without changing the password yet.After all payloads were tested i found that one particular payload had returned with a different response so that confirmed that was the correct username.Then i intercepted another user login request with correct username and a random password. Then i did the same attack for entered password. Then after observing the payload tests, i found that one of the payloads had strange length value and different status value . I tried logging in using the correct username and this password and it was successful.

For the second lab, i first login into my crendentials and went through the 2FA verification and then accessed the my account page and saw the url path for that page. Then i tried to login to the carlos account and in the verification page , i changed the url path to the mmy account page for carlos and it worked.

### Learnings:
I learnt how burp suite application is used to intercept and manipulate the HTTp requests sent out to the server and how specific attack methods can be carried out using the intruder tool.
