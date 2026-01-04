# Server-side vulnerabilities

## Path traversal

### Solution:
To get to the target file, i used this ```bash /image?filename=/../../../etc/passwd``` which i found using the inspect tool that files were being accessed in this manner and solved the challenge. 

### Learnings:
I learnt what Path transversal vulnerability was and how it can be exploited by attackers.


