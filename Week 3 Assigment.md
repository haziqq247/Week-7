Muhammad Haziq Iskandar Bin Zulzahari	

52215225215

Lab assignment

Step 1 : Reconnaissance

Objective : The purpose of this phase is to identify the target’s attack surface and enumerate any exposed services.

Start with nmap to scan the open port
nmap -sC -sV -Pn -vv 10.150.150.11

<img width="756" height="514" alt="image" src="https://github.com/user-attachments/assets/407fc2eb-d3f0-499b-8b36-d2d5baae65d5" />
<img width="755" height="454" alt="image" src="https://github.com/user-attachments/assets/de0ab9e1-404d-4c65-99f1-98db2b99aaca" />
<img width="756" height="514" alt="image" src="https://github.com/user-attachments/assets/265c3685-1874-4de8-901c-4eb2ed0ae3f0" />



Step 2 : Scanning & Enumeration

Objective: To gather deeper and more detailed information from the previously identified services.

<img width="759" height="505" alt="image" src="https://github.com/user-attachments/assets/2831fcd0-f19c-4fcc-aa34-ae228154166e" />

Discovered /upload /admin

<img width="713" height="278" alt="image" src="https://github.com/user-attachments/assets/ce4dacc3-d3df-43eb-92e9-11e66813f490" />

Directory indexing is enabled on the exposed /upload path, indicating insufficient access restrictions. Combined with file upload capability, this may allow an attacker to introduce arbitrary files, including executable scripts, which could result in remote code execution.

<img width="720" height="298" alt="image" src="https://github.com/user-attachments/assets/c173d51f-6f85-4a1f-8c39-d1f2c88cc539" />

<img width="893" height="480" alt="image" src="https://github.com/user-attachments/assets/0d39d545-eaf0-4fac-913b-d69e0e2c5b61" />


3.Gaining Access

To exploit identified vulnerabilities in order to establish an initial foothold on the target system.

Create a new admin with username:testadmin

<img width="872" height="359" alt="image" src="https://github.com/user-attachments/assets/9fe25ce0-2135-4caf-b2f6-0bef45867e71" />

Try opening manage user

<img width="915" height="374" alt="image" src="https://github.com/user-attachments/assets/ec725566-20bf-47eb-955d-61fb5023a7ce" />

Making exploit vulnerability by uploading malicous PHP file and uploading reverse shell

<img width="961" height="429" alt="image" src="https://github.com/user-attachments/assets/0307c13d-558c-4e82-bf59-71486e9703a8" />

Try command injection

<img width="641" height="243" alt="image" src="https://github.com/user-attachments/assets/3d7471e3-c4cc-40dd-bc31-54e1b1b74a88" />


<img width="741" height="233" alt="image" src="https://github.com/user-attachments/assets/6acf842b-218c-4ba8-8df6-0a4ea5686067" />

Maintaining Access

Establish control and explore system.

<img width="629" height="202" alt="image" src="https://github.com/user-attachments/assets/90a1cb60-9b5b-4e17-a4a7-74f4fa964f04" />

<img width="921" height="254" alt="image" src="https://github.com/user-attachments/assets/76e6d866-3680-43e8-932f-b3d570a54483" />

<img width="921" height="283" alt="image" src="https://github.com/user-attachments/assets/89ee9e3c-7ffa-48e6-adc8-1e890f6ba81f" />

<img width="947" height="192" alt="image" src="https://github.com/user-attachments/assets/b00a9bf1-c0fb-4c52-886a-2be891216056" />



















 



 

