# 1. Linux CLI - Shells Bells

## Solution:
Basically i opened the virtual machine and ran the ls command with -la argument to list the hidden files and catted the first flag. For the second flag, i changed the directory to /var/log then i ran the grep command with the keyword "Failed password" in the auth.log file. For the third flag i switched to root user by using the sudo su command then i checked the bash history by catting the .bash_history file.

## Learnings:
i revised the usage of ls -la command to get hidden files in the pwd and how the logins can be viewed in auth.log of /var/log directory. Also i learnt that bash history can be viewed as the root user.

# 2. Phishing - Merry Clickmas

## Solution:
i ran the login page script in the terminal using the server.py file. Then i ran the SET using the setoolkit command then selected the social engineering attack called the  Mass Mailer Attack and used it to send an email attack to one of the worker's email using a source email id and fabricated a fake email content to make it believable.This led to the worker typing out the login credentials and the login page got me those and i found that the password was reused for factory user and acessed his mail to get the expected toys quantity. 

The login page script running in the terminal:
<img width="678" height="478" alt="image" src="https://github.com/user-attachments/assets/09dd06c4-5546-40f0-afcc-1b90f82a4398" />

## Learnings:
i learnt about the various applications of Social engineering and it is used to exploit and get access to sensitive data of user by allowing them to be deceived by various media means. Also learnt how setoolkit can be used to create such attack vectors.

# 3. Splunk Basics - Did you SIEM?

## Solution:
i used the splunk application to identify the malicous attacker's activity by searching through the internal logs. I got the attacker's ip address by viewing the highest malicious web traffic from an external ip. On further searching and analysing the web traffic source, we found attempts to find path transversal vulnerabilities and SQL vulnerabilities exploitations. Also the webshell was used for payload delivery. Final confirmation of malicicous activity was given by the connection of the compromised server with the attacker's ip. 

## Learnings:
I learned how splunk application can be used for searching the internal logs and filter out essential info about attacker's malicicous activities.


# 4. AI in Security - old sAInt nick

## Solution: 
I used the AI tool to get the python script that can exploit the SQL vulnerability of a website. Then it helped to analyse the logs to get info about the attempted exploit which is very essential form Blue team perspective. Then i finally completed the showcase for the first flag and then i used that python with my attack machine ip to get the second flag.

## Learnings:
I learned how ai tools can be used to create scripts for exploitation and also it can help detect vulnerabilities through analyses of logs.

# 5. IDOR - Santa’s Little IDOR

## Solution: 
i answered the questions using the info from the description.I kept altering the user id in the local storage using developer tools to find the parent with 10 children.

## Learnings:
I learned what IDOR was and it can be exploited by the attacked if not prevented.


# 6. Malware Analysis - Egg-xecutable

## Solution: 
i used the PeStudio to do static analysis of the HopHelper.exe application and got the cchecksum in the sha256 property and the second flag in the strings identifier. For dynamic analysis i first took a snapshot of the system using RegShot and then i took another after executing the malicious application and compare both to find the registry path of the executable in thhat log. Then i capture the system events after executing the malicicous application in ProcMon and used filters to get the network type used by the application.

## Learnings:
I learned what are static and dynamic analysis of malicicous applications and how they are carried out by using different application to analyse it better.

# 7. Network Discovery - Scan-ta Clause

## Solution: 
i opened the QA website and then scanned all machine network ports along with an argument to see what is likely behind the port.This got me the port number of the tbfc application that is running on FTP server.Using the ftp command with machine ip address and the network port, i got the first key. IN order to interact with unknown network service of the second network port , i used the netcat tool and then used its commands to get the second flag. For the third flag i scanned the UDP ports using nmap command with -sU argument. THius returned that there is a open port associated with DNS so i used dig tool to pass a query regarding the third flag and got it. After using these keys i got accessed to web-hosted terminal and then i listed the listening ports. then by  using the mysl program i accessed the database and got the final flag.

## Learnings:
i learned how different tools like nmap and netcat can be used to scan port of different network services.

# 8. Prompt Injection - Sched-yule conflict

## Solution: 
I sent a hello prompt and observed that it was revealing the functions in the system amd their applications.So the calendar could be reset using the reset_holiday function with the appropriate token.To get this i used the get_logs function and used this token to reset the calendar to get the flag.

## Learnings:
I learned how prompt injection in agentic AI worked to get access of the system.

# 9. Passwords - A Cracking Christmas

## Solution:
For the hidden flag in the pdf file i used the dictionary attack using pdfcrack and rockyou.txt and got the password to open the pdf. For the second flag in the locked zip file, i used the zip2john to create a hash and then used the --show as argument to get the password.

## Learnings:
I learned how tools like pdfcrack and zip2john can be used to execute dictionary attacks onto different file types to get their passwords.

# 10. SOC Alert Triaging - Tinsel Triage

## Solution:
 For the assessment of Task 4, i simply viewed the respective attributed of the inciidents mentioned in the questions.For the task 5 assessment, i kept changing the host_s to mentioned application and got the answers.

## Learnings:
I learnt about the alert triaging and how Microsoft Sentinel can be used to identify and analyse the log data before and after the alerts.

# 11. XSS - Merry XSSMas

## Solution:
I used a payload to display an alert and that the first flag was returned in the search which confirmed reflected xss. Then i sent similar payload as message to execute a stored xss and it worked to get the second flag.

## Learnings:
I learnt how XSS vulnerability can be explited to get access to sensitive info in web applications and how reflected xss and stored xss can be used to exploit it in different ways.

# 12. Phishing - Phishmas Greetings

## Solution:
In the Warevilla Email Threat Inspector, i identified different phishing techniques and determined it was phishing email or spam email to get each flag. 

## Learnings:
I learnt how different phishing techniques like spoofing, impersonation, social engineering texts, fake invoices, malicious attachments,etc are used to trick people and exploit them to commit various cyber crimes.

# 13. YARA Rules - YARA mean one!

## Solution:
I wrote a yara rules script to get the files that contain the string "TBFC:" followed by any alphanumeric strings.Then i used the -r argumnet with yara command to scan the target directory and then i used the -s as argument with yara command to get the hidden message in the files.

## Learnings:
I learnt how to write a script using yara rules to scan or get required data using search strings and also different conditions to makee this search more convinient.

# 14. Containers - DoorDasher's Demise 

## Solution:
First i used the command ```bash docker ps ``` to view the running services. Then i tried to access and check out the uptime-checker container and verified that API can be interacted from there by running the docker commands inside the container. Then i went onto check the priviledged container "deployer" using the command
```bash docker exec -it deployer bash ``` and then ran the recovery_script to recover the app and then catted the flag present in the root directory.

## Learnings:
I learnt what containers are and how docker application can be used to build, deploy and mandge containers.


# 15. 

## Solution:


## Learnings:







