<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 11</b> (21H2)

<h2>List of Prerequisites</h2>

Item 1. Web Server

Item 2. PHP 8.0+: Language osTicket uses to work.

Item 3. PHP Extensions: Needed tools like mysqli, gd, imap, mbstring, etc.

Item 4. MySQL 5.5+: Stores tickets and user data.

Item 5. Email Server: Sends/receives support emails (SMTP/IMAP).

Item 6. OS: Any system (Windows/Linux) 

Item 7. Browser: Chrome, Firefox, or Edge to access it.

<h2>Installation Steps</h2>
Step 1. Create a new Resource Group (this can be created under the VM create)
•	Name it osticket

![image](https://github.com/user-attachments/assets/48aeb935-eab3-467a-9c0e-cddd878220d1)

Step 2. Create an Azure Virtual Machine Windows 11, 4 vCPUs
•	Name: osticket-vm – of the VM
•	Region: (US) Central US
•	Image: Windows 11 Pro
•	Username: labuser
•	Password: OsticketPassword1
•	Be sure to check the box under Licensing and continue to Networking
•	Let it create a new virtual network
•	Then click Review & Create

Step 3. Obtain the Osticket-vm IP address, as you’ll need it for the Remote Desktop.
![image](https://github.com/user-attachments/assets/16e4011e-5f2c-45c0-92aa-fbc8d75c46c2)

Step 4. Login to the VM using the IP with the Remote Desktop

![image](https://github.com/user-attachments/assets/eab8b7ed-95bf-4d4f-9bac-4ed93ff701f7)

•	Once logged into the VM, open the internet browser and click past the prompts asking to keep data 

Step 5. Within the VM (osticket-vm), download the [osTicket-Installation-Files.zip](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) and unzip it onto your desktop. The folder should be called “osTicket-Installation-Files”
• We will use the files in this folder to install osTicket and some of its dependencies.
•	In the VM web browser, paste the link and download
•	Open the folder and drag it onto the Desktop
•	Then right-click the folder and select “Extract All.”
![image](https://github.com/user-attachments/assets/044465ab-a241-40a6-b3e8-33739f97fcbd)

Step 6. Install / Enable IIS in Windows WITH CGI
•	Click Start and go to Control Panel
•	Go to Programs, and on the left, you will see Turn Windows Features On/Off.
•	Check Internet Information Services
•	Then World Wide Web Services
•	Then, Under Application Development Features, Select CGI. 
![image](https://github.com/user-attachments/assets/15779579-b1d5-470b-8f97-5cdb04ebeeed)

Step 7. Install PHP Manager
•	Locate the File inside the osticket folder on the desktop and just click I agree. 
![image](https://github.com/user-attachments/assets/e696fec2-3661-4cb7-9e2d-4d621368ba4f)

Step 8. Install Rewrite Module
•	Locate the File inside the osticket folder on the desktop and just click I agree. 

Step 9. unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder
•	Click on File Explorer
•	Click on the Windows C and create a new Folder called “PHP”
![image](https://github.com/user-attachments/assets/e3f11c65-2dfa-4487-9b58-71a85f32126c)

•	Inside the Osticket installation folder, right-click php-7.3.8 and click Extract All
•	Be sure to select the browser and select the PHP folder that was just created 
•	You’ll notice all the files are now in the folder PHP and should look like this
![image](https://github.com/user-attachments/assets/d6f53a21-8e47-4b75-846b-94a02d940c4f)

Step 10. Install [VC_redist.x86.exe](https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view?usp=share_link).
•	Locate the File inside the osticket folder on the desktop and just click I agree. 

Step 11. Install [MySQL 5.5.62](https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view?usp=share_link)
•	Locate the File inside the osticket folder on the desktop and just click I agree. 
•	Be sure to select “Typical” when installing
•	Be sure to choose “Standard Configuration.” 
•	Username: groot
•	Password: groot
•	Then click next and execute

Step 12. Click Start and type ISS, and click Run as Admin
•	Register PHP in ISS by clicking on it and click register
•	Then browse to it by clicking the three dots and select the PHP folder in Windows C
![image](https://github.com/user-attachments/assets/409217f0-d27d-4019-90f6-34ba789b8700)

Step 13. Reload IIS (Open IIS, Stop, and Start the server)
![image](https://github.com/user-attachments/assets/ace6f96c-414f-4094-aabd-ec145319b053)

•	Step 14. Install OsTicket from the OsTicket folder 
•	Right click and select Extract All on the OsTicket folder 
•	You will see a new Folder 
![image](https://github.com/user-attachments/assets/a8bb6169-4bd9-4ec3-a555-006a2ee7faf4)

Step 15. Copy the Upload Folder to Windows C
•	Click on inetpub – then wwwroot 
![image](https://github.com/user-attachments/assets/44f23cd7-59fd-4d21-935b-f937cb18457d)

•	Reload IIS (Open IIS as Admin, Stop and Start the server)


Step 16. Open the osTicket Site

![image](https://github.com/user-attachments/assets/18a40924-e6c8-4899-9d07-75d77cc1367f)

Congratulations, OsTicket is installed! 
![image](https://github.com/user-attachments/assets/191d24a7-0583-440a-9efd-1d751fc2aecd)


