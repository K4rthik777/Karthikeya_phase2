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

