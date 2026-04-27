Week 4 Metadata
Assigment
Tool learned:
1.	file
2.	strings
3.	exiftool
4.	hexeditor
5.	binwalk

Ocean.jpg
<img width="909" height="456" alt="image" src="https://github.com/user-attachments/assets/7da7de1a-fce4-470e-a8cd-d4f6fda3654d" />
 
 
The hidden flag was found using ExifTool by analyzing the image metadata. It was stored in the “Comment” field of the JPEG file, which is not visible when viewing the image normally. This shows that hidden data can be embedded in metadata without changing the image appearance.

Computer.jpg
<img width="890" height="433" alt="image" src="https://github.com/user-attachments/assets/a49755ea-faac-4ab4-ba0f-a1cde28abf27" />
 
 
The file was also analyzed using a hex editor to examine its raw binary data. The hex view displays the file in hexadecimal format, allowing deeper inspection beyond normal viewing methods. In this case, the data appears mostly empty (filled with zeros), indicating no additional hidden content in this section. Hex editors are useful in digital forensics to detect hidden or modified data within a file.
 

Dog.jpg
<img width="882" height="700" alt="image" src="https://github.com/user-attachments/assets/501f0d43-e639-4288-a728-85a41a6e833a" />
 

 
That file has be analyze by using Binwalk to detect embedded files within it. The tool identified a hidden ZIP archive inside the JPG file, which was then extracted. After extraction, a text file named “hidden_text.txt” was found, containing the hidden flag. 

 
Computer.jpg
<img width="928" height="525" alt="image" src="https://github.com/user-attachments/assets/60d09826-a471-4bb5-bf32-d3a8b86ef74d" />
 
 
The image was analyzed using an online strings extractor tool to retrieve readable text from the file. The extracted output mostly contained random and unreadable characters, indicating that no obvious hidden flag was stored as plain text within the image data.

 
Solitaire.exe
<img width="1149" height="553" alt="image" src="https://github.com/user-attachments/assets/a94d1396-616d-4af0-9f4b-d596b658798a" />
 
The file was analyzed using the “file” command, which revealed that the supposed executable file was actually a PNG image. This indicates that the file extension was intentionally misleading. So this doesn’t work or exe file
 

Rubik.jpg
<img width="1150" height="241" alt="image" src="https://github.com/user-attachments/assets/13e83863-3a51-4902-bb4b-ef932ec2b748" />
 
 
The analysis showed that although the file has a .jpg extension, it is actually a PNG image file. This was confirmed using the file command, which identified it as “PNG image data.” This indicates that the file extension was misleading or intentionally changed, a common technique used to hide the true file type in digital forensics.
