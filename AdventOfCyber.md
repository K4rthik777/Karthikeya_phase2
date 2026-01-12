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
First i used the command ```docker ps ``` to view the running services. Then i tried to access and check out the uptime-checker container and verified that API can be interacted from there by running the docker commands inside the container. Then i went onto check the priviledged container "deployer" using the command
``` docker exec -it deployer ``` and then ran the recovery_script to recover the app and then catted the flag present in the root directory.

## Learnings:
I learnt what containers are and how docker application can be used to build, deploy and mandge containers.


# 15. Web Attack Forensics - Drone Alone

## Solution:
In the SOFTWARE hive in the attackbox, i searched for any application installed which could have any clue for this challenge and found the DroneManger Updater.Then in Registry Explorer, I searched the user hive for the dispatch.admin user and checked the entries which revealed the application run path. For checking any persistence left behind after the application has run, i checked the SOFTWARE hive again in the run directory and found a suspicious executible called dronehelper.exe

## Learnings:
I learned how the hives need to be used to investigate any particular malicious applications and which directories are to be searched for getting info about a particular aspect regarding the application.

# 17. CyberChef - Hoperation Save McSkidy

## Solution:
I followed the instruction given innthe description of teh challenges and did the encoding of the text into Base64 using cyberchef and also used XOR if mention using the tools in the cyberchef to clear each level of the challenge. I also used the HEX and reverse tools for the last level and got the assword and the final flag.

## Learnings:
I learnt how Cyberchef tools can used efficiently for any encoding/decoding techniques and also for various functions can be carried out using the Cyberchef application.

# 18. Obfuscation - The Egg Shell File 

## Solution:
For this part 1, i deobfuscated the given string using "From Base64" and got an url which i pasted into one of the variable and got the first flag. For the part2, i deobfuscated the given string using "XOR" with key as 0x37 and then convert that into hexadecimal and pasted that into another variable in the script and ran it to get the second flag.

## Learnings:
I learnt how Obfuscation can be used to evade tracking software and exploit the system.

# 19. ICS/Modbus - Claus for Concern 

## Solution:
For the practical i did a reconnissence of the ports using nmap and found that the port 80 was a HTTPS service port and the port 502 is ModBus TCP.Then i ran reconnissence python to thoroughly checkout the ports but it had fail to restore the ports then i used another python script to restore these ports and this got the flag.

## Learnings:
I learnt about SCADA systems, ModBus, and PLCs and how these can be exploited by the attackers and how these Modbus ports can be restored by using python scripts.

# 20. Race Conditions - Toy to The World 

## Solution:
First i placed an order for the Sleigh toy and then went onto the burpsuite to find the POST requestion with /process_checkout. After finding it i sent it to the repeater and create a tab group with multiple duplicates of the original request and then simultaneously sent these request to initiate a race and get the flag.

## Learnings:
I learnt what race conditions were and how can be triggered by attackers to exploit web applications and also howw to mitigate for such vulnerabilities.

# 21. Malware Analysis - Malhare.exe

## Solution:
I viewed the HTA file in the attacker box using pluma and fouund the title of the application in the header itself.Then i found that there was obfuscationa and social engineering elemnets in this script and found that the function getQuestions in the VBscript was exfiltrating the data using objects.Then i decoded the text given in one of the questions and found it was in Base64 and then  i got the encoded flag which was in ROT13.

## Learnings:
I learnt how HTA can be used for automation by defenders and also how these can be used to deliver malicious code and launch them directly into the powershell of the desktop.

# 22. C2 Detection - Command & Carol

## Solution:
I used the zeek command with the challenge pcap file and parse it into a directory in the system - ``` zeek readpcap pcaps/rita_challenge.pcap zeek_logs/challenge```. Then i used this command ``` rita import --logs ~/zeek_logs/challenge/ --database challenge ``` and import the logs data from the pcap file to this new database. Then using this command ``` rita view challenge ``` i analysed the connections made to the malhare.net and answered the questions.

## Learnings:
I learnt how to use zeek tool to parse pcap file and also how rita tool can be used to view and analyse the contents of the pcap files by converting required logs data into databases.

# 23. AWS Security - S3cret Santa

## Solution:
I used the command to get to know the working id ```aws sts get-caller-identity``` and then i tried to find the IAM role by using the IAM policies attached to the current id ```aws iam list-user-policies --user-name sir.carrotbane ``` with this command. Then i listed all the roles using ```aws iam list-roles``` and found a role called buckmaster and listed its policies. I tried to get the temporary credentials to enable me to assume that roles using this command ``` aws sts assume-role --role-arn arn:aws:iam::123456789012:role/bucketmaster --role-session-name TBFC``` and after getting these detail i export those as variables and assumed that role. With this new role i got access the S3 bucket so i listed all buckets and found one that could contain the flag. So i tried to copy its contents to a txt file to get the flag. 

## Learnings:
I learnt about the AWS system and how IAM roles are established using userIds, SecretAccessToken and also SessionTokens . Also i learnt how to assume other roles to get additional access permissions to carry out tasks.

# 24. Exploitation with cURL - Hoperation Eggsploit 

## Solution:
First i made a POST request to the /post.php endpoint with the username admin and the password admin using ``` curl -X POST -d "username=admin&password=admin" http://10.49.156.132/post.php``` to get the first flag. Then i went on to make a request to the /cookie.php endpoint with the username admin and the password admin using ``` curl -c cookies.txt -d "username=admin&password=admin" http://10.49.156.132/cookie.php```and save the cookie to cookies.txt using ``` curl -b cookies.txt http://10.49.156.132/cookie.php``` to get the second flag.Then i did the brute force on the /bruteforce.php endpoint using ``` curl -A "TBFC_SpecialAgent" http://10.49.156.132/agent.php``` and got the third flag. Then i made a request to the /agent.php endpoint with the user-agent TBFC using ``` curl -A "TBFC_SpecialAgent" http://10.49.156.132/agent.php``` and got the final flag.

## Learnings:
I learnt how to use curl to send http request to web server in the absence of a browser and also learnt how to bruteforce a user password and access session cookie using user credentials. 





