#Week 7 Assigment


Question 1: Analyse packet1.pcap and find the flag. 

<img width="1918" height="536" alt="Screenshot 2026-04-27 161659" src="https://github.com/user-attachments/assets/cc1518cf-9c2a-46b4-a435-35ca0e001e0f" /> 
 

 
<img width="1331" height="24" alt="image" src="https://github.com/user-attachments/assets/6d272113-ea5e-4532-9bcb-efeeece61205" />



<img width="1659" height="479" alt="image" src="https://github.com/user-attachments/assets/201b4f7a-a794-46b4-b5a3-7c9f26125120" />

Decode the text by using Base64 converter


<img width="1425" height="761" alt="image" src="https://github.com/user-attachments/assets/5faa4d50-8e50-4763-951f-41c9a5b0ce8c" />

We already get the flag : SUCTF2023{ai_is_cool}


Question 2: Analyse packet2.pcap and find the flag.

<img width="1912" height="553" alt="image" src="https://github.com/user-attachments/assets/d682d3a5-e241-4a92-b9c2-1e4568319e7a" />


Searching tcp.port == 37697 to find the ftp

<img width="1913" height="261" alt="image" src="https://github.com/user-attachments/assets/e80c1b1e-e456-481b-b5ed-ab58f3153a74" />


<img width="586" height="178" alt="image" src="https://github.com/user-attachments/assets/34987c8f-28cf-4732-812d-717688e0dafe" />

Paste the link into google

<img width="868" height="413" alt="image" src="https://github.com/user-attachments/assets/68455695-085f-4ec3-ab9f-66e36b43bc9d" />


Question 3: Interpret an Nmap Output

1. What can an attacker do with each port?
Port 21 (FTP – vsftpd 2.3.4)
Attempt anonymous login or brute-force credentials
Upload/download files
Potentially gain a shell if exploited

Port 22 (SSH – OpenSSH 5.3p1)
Attempt brute-force login
Gain remote command-line access if credentials are weak

Port 80 (HTTP – Apache HTTP Server 2.2.8)
Browse the website
Exploit web vulnerabilities (e.g., file inclusion, outdated modules)
Enumerate directories or sensitive files

Port 139 (NetBIOS)
Enumerate shared resources
Gather usernames and system information

Port 445 (SMB – Windows sharing)
Access shared folders
Attempt authentication attacks
Exploit SMB vulnerabilities

2. What vulnerabilities are likely present based on the version?

FTP – vsftpd 2.3.4
Known backdoor vulnerability.
Can give attacker remote shell access

SSH – OpenSSH 5.3p1
Possible known exploits.
Vulnerable to brute-force attacks

HTTP – Apache HTTP Server 2.2.8
Multiple known CVEs
Vulnerable to Directory traversal. 
Remote code execution (depending on config)

SMB – Windows 7 Professional SP1
End-of-life OS
Vulnerable to EternalBlue.
Wormable attacks (e.g., WannaCry)

4. Which one is the highest risk and why?
5. What attack path can be built from this?
6. What should be the remediation?


