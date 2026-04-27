Week 2 Bluemoon
1. Reconnaissance

<img width="860" height="361" alt="image" src="https://github.com/user-attachments/assets/05ab7f64-ff67-418a-87a6-6bd3c754efc4" />

 
Find the IP address of the BlueMoon virtual machine in my Kali network. Use “netdiscover” command to scan the network and identify the target IP.


2. Scanning
<img width="866" height="683" alt="image" src="https://github.com/user-attachments/assets/b053c484-ed57-4544-80bc-0b352cb400dc" />
 
Once get the ip address, ran the nmap to check for all open port,from the result there are were three open port. That a FTP,SSH and HTTP
 
<img width="873" height="628" alt="image" src="https://github.com/user-attachments/assets/6b1a23d2-42cb-4373-96fc-02e3ae442e61" />
 
Use “gobuster” command to perform directory brute-force and finde the hidden directory that called hidden _ text

<img width="867" height="476" alt="image" src="https://github.com/user-attachments/assets/4d6b9af3-b20c-4ac2-81a3-9f27b79ffa6e" />
 
The page look like just an empty browser, checking the page source and notice there a hidden image file.
 
<img width="261" height="260" alt="image" src="https://github.com/user-attachments/assets/ba5a36c4-5b1a-4a6a-ab28-fc1ae3459f42" />

<img width="853" height="299" alt="image" src="https://github.com/user-attachments/assets/25dc577e-b6f3-4c9f-b9dd-ce16be70b9b8" />

 
After download that image and drag It to desktop, tried to extract the information from the images. And found out there are important detail inside, including username and password.

3. Gaining access
<img width="857" height="390" alt="image" src="https://github.com/user-attachments/assets/94de77b3-4e78-45a0-bc6e-ed3967463687" />

 
Use the credentials, logged into the ftp server. There are 2 txt file. Information.txt and p_plists.txt. The information.txt mentioned a user named robin, and the p_list.txt contained a list of possible passwords.
<img width="870" height="588" alt="image" src="https://github.com/user-attachments/assets/11c4298b-40df-49a5-85db-ce464cdae643" />

<img width="882" height="638" alt="image" src="https://github.com/user-attachments/assets/1dd36a0f-bbe5-4d9f-b51c-602b90ffe33b" />

 
Hydra to brute-force the SSH login for robin using the password list. As the image shows the hydra succesfully find the password for the user robin.
<img width="904" height="676" alt="image" src="https://github.com/user-attachments/assets/19cacd4b-b49d-47d6-be55-b779b446295d" />
 
Ssh login as robin, there a home directory inside. And found the first flag
 
4. Escalate Privilage
 
<img width="864" height="309" alt="image" src="https://github.com/user-attachments/assets/ab9554aa-59d1-491d-a6e1-3aeabedba939" />

<img width="864" height="547" alt="image" src="https://github.com/user-attachments/assets/7cfc3e08-3147-4c15-b913-1f8cf015a946" />

Executed the script and managed to spawn a shell using /bin/bash, which gave the access as jerry. From there, found the second flag in jerry’s home directory

<img width="874" height="512" alt="image" src="https://github.com/user-attachments/assets/f93b5169-e840-4420-8a09-12957c07722b" />

 
There a docker group. This is important because docker can be use for privilege escalation.

<img width="861" height="600" alt="image" src="https://github.com/user-attachments/assets/f4bee6e4-f00b-491a-b471-ee4e387452fc" />

Found the last flag in root directory


