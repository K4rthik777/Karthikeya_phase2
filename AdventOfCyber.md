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


# 4. 

## Solution:


## Learnings:


