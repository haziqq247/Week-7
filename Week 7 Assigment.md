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

1.What can an attacker do with each port?
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

2.What vulnerabilities are likely present based on the version?

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

3.Which one is the highest risk and why?


Port 445 (SMB – Windows 7) is the highest risk because of known critical exploit (EternalBlue) and no authentication needed in some cases

4.What attack path can be built from this?


Start with Port 80 (web) → gather info / find entry point

Use Port 21 (FTP) → exploit vsftpd backdoor → get initial shell. 

Move laterally using Port 139/445 (SMB) → enumerate shares

Exploit EternalBlue on Port 445 → gain full system access

Maintain access via SSH (Port 22) if credentials found

5.What should be the remediation?

Disable or update vsftpd 2.3.4 (remove backdoor risk) and upgrade OpenSSH to latest version

Question 4: Identify the OS (OS Fingerprinting) - TTL

Image 1

<img width="628" height="223" alt="image" src="https://github.com/user-attachments/assets/af9d847b-f38c-4a52-8835-0526986e4e55" />

It showing a ttl value, that shows the packet is still at its initial value, meaning it stayed within the local machine and did not travel across any network devices

Image 2

<img width="346" height="237" alt="image" src="https://github.com/user-attachments/assets/b6ef1de4-a95d-418f-badb-ce87ec749f94" />

TTL here is 255, which means the packet started with a maximum TTL value and has not passed through many routers yet

Image 3

<img width="643" height="141" alt="image" src="https://github.com/user-attachments/assets/b92d8858-49dd-4a1b-b0d1-228b037f1c64" />

This output shows that your computer is sending ICMP echo requests (ping) to the IP address 192.168.122.239 and receiving replies successfully.

Question 5: Analyse the Nessus file
Upload to your nessus (Network_Scan.nessus) and analyse the files. Focus on critical or high findings that was identifies in analysis named “Ghostcat”.

<img width="1319" height="511" alt="image" src="https://github.com/user-attachments/assets/a520a95d-fc5d-4304-9817-4578a6074b1d" />

1.What is the affected Port number

<img width="276" height="57" alt="image" src="https://github.com/user-attachments/assets/1c1c9860-bd74-4cf8-8103-60e7f6946966" />

2.What is the Affected protocol

Apache Tomcat AJP

3.What is the CVSS Score of vulnerability found

<img width="323" height="85" alt="image" src="https://github.com/user-attachments/assets/7a43ad44-0b5f-4ed8-a22e-60a3a7cb6ca2" />

4.Can you find any exploit related to this vulnerability? 

Yes, there are public exploits available for Ghostcat (CVE-2020-1938) that allow attackers to read sensitive files and potentially achieve remote code execution via the AJP port

5.Find CVE for this vulnerability.

CVE:  CVE-2020-1938, CVE-2020-1745










