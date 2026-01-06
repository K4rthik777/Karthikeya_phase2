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
I learnt how burp suite application is used to intercept and manipulate the HTTP requests sent out to the server and how specific attack methods can be carried out using the intruder tool.

## Server-side request forgery

### Solution:
For the first lab, i opened in the burp browser and intercepted the HTTP requests. Then i viewed one of the product stock and in the intercepted request i altered the stockapi to the ```bash http://localhost/admin ``` and got the admin page . There i tried to delete the carlos user but it didn't work. So this time again check the product stock and altered the stock api url but this time i directly changed it to the url to delete the carlos user and it worked.

For the second lab, i followed the same process upto intercepting the stock api url and then i changed it to the /admin page and i highlighted the single 1 in the ip address and sent it to the intruder to test out the range and get the correct number for admin access. i set the range upto 100 and i got the number to be 14 . So i tried accessing the admin page using this and it worked.Then i changed the stock api url to directly delete user carlos.  

### Learnings:
I learned how server side vulnerability can be critcal and exploited. Also i learnt how numbers can also be passed as payloads in request using the intruder.

## File upload vulnerability

### Solution:
For the first lab, i logged into the wiener user account and uploaded random image and checked the request in the proxy tool and observed the the path of the image followed by the server after uploading. Then i created a php file and with this in it ```php <?php echo file_get_contents('/home/carlos/secret'); ?>``` and upload this file to the server. Then i observed a GET request for this php file and i sent it to the Repeater and sent the request to the server and got the secret code.

For the secoond lab, i followed the same process upto intercepting the upload request of php file, there i changed the content-type to image/jpeg and forwarded it. Then i got the GET request for the php file and sent it to the Repeater and sent the request to the server and got the secret code.

### Learnings:
I learnt how file upload vulnerability can be exploited by manipulating the uploaded file type in the http request using burpsuite's Repeater tool . Also i learnt how php file can be crafted to created webshells to execute any commands as attacker.

## OS command injection

### Solution:
For this lab, i opened the productID parameter in the repeater and then first i tried using ```bash &whoami&``` as in example but it didn't work.So i tried using or operator instead to get it to execute the command  ```bash |whoami|``` and it worked to give peter as the user.

### Learnings:
I learnt how OS command vulnerabilites can easily compromise sensitive info from the internal system.

## SQL injection

### Solution:
For the first lab, i changed the url to category Gifts to ```bash /products?category=Gifts' OR 1=1--``` and the unreleased product also got shown.

For the second lab, i entered the username as administrator'-- in the login page with a random password and got the access for administrator page.

### Learnings:
I learnt how SQL injection vulnerability can lead to leakage of sensitive data from internal databases and gives multiple ways for the atttackers to exploit the applications.
