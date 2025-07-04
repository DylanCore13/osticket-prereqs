# osTicket-prereqs
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

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Laptop and working Internet of course
- Active Azure subscription (Can pay for it or apply for a Free Tier/Trial)
- Downloaded osTicket-Installation-Files -> https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0


<h2>Installation Steps</h2>



<p>
Start by creating a virtual machine in Azure, you can search it up in the serach bar or clicking on it at home page at the top where it virtual machines. After that you're going to create an Azure Virtual Machine Windows 10, 4 vCPUs


</p>
<br />

![Step 1](https://github.com/user-attachments/assets/34cb320e-9e10-4bb7-bd7d-239fcfb95a5e)

![step 2](https://github.com/user-attachments/assets/7413fb73-4754-499d-b5ae-147ff30d3731)


<br/>

<p>
There's a ton of ways custiomize and setup your virtual machine, your going to see catagories around saying, Basics, Disks, Networking, Management, Monitoring, etc. Know that you'll only be using Basics to set it up. Create a new resource group, name it the same as the virtual machine if you'd like. Here's how the set up goes from here.

- Region: (US) East US 2
- Availability options: Zone options - SELECT "self selected zone"
- Availability zone: Zone 1
- Security type: Trusted launch virutal machines
- Image: Windows 10 Pro, Version 22H2
- VM architecture: x64
- Size*: Standard_E2s_v3 - 2 vcpus, 16 GiB memory
- DO NOT ENABLE HIBERNATION!!!
- Username: labuser
- Password: osTicketPassword1!
- Public inbound ports*: Allow selected ports
- Select inbound ports*: RDP(3389)


At the bottom it will make check a box after that just click "review+create" this will make Azure validate the virtual machine you wnat to launch making sure it will work. You will probably have to click create again.

</p>
<b/>


![image](https://github.com/user-attachments/assets/767435a4-461f-4337-8197-def9a2c39ef4)

<b/>



<p>
 
After it created you will have to copy public IP address and open remote desktop connection from start button or search it up.

 
</p>
<br />

![image](https://github.com/user-attachments/assets/3c8daaad-e246-4773-a031-75db2f91dcf9)


<p>
Copy and paste it into the computer bar and it will ask to log in with username and password you set up when creating the virtual machine. From there connect and you will be logged in into a VIRTUAL MACHINE/COMPUTER.
</p>
<br />

![image](https://github.com/user-attachments/assets/54095197-abc1-4a35-b556-0943ce041c18)
<b/>

<p>
Remember that you'll be doing everything from here on out ON THE VIRTUAL MACHINE!!! Next you will have to download the osTicket Installation files on the virtual machine.
 
- https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0


Within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip it onto your desktop. The folder should be called “osTicket-Installation-Files”
We will use the files in this folder to install osTicket and some of the dependencies.


![image](https://github.com/user-attachments/assets/2caeaac2-a19f-4fa6-8e12-aee948d4bb1b)

<b/>




Open Control panel, click on unstall program. CLick on Turn Windows features on or off on left side. Click on check box where it says "Internet Information Services" than click on + marker on left side to reveal more features, click on + marker again on "World Wide Web Services". Finally click on + marker for "Application Development features". Check box CGI

![image](https://github.com/user-attachments/assets/62f78445-a1b7-4bcb-9be4-2efd98773164)

<b/>



From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

![image](https://github.com/user-attachments/assets/2caeaac2-a19f-4fa6-8e12-aee948d4bb1b)

<b/>

Go to C:\ and create a new folder and name it PHP


![image](https://github.com/user-attachments/assets/ea8d9a31-0f9f-4e97-85e6-26c239414ac6)





From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder



![image](https://github.com/user-attachments/assets/fdce7e0e-2278-4163-ba68-df701a0c63e1)


From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

![image](https://github.com/user-attachments/assets/2caeaac2-a19f-4fa6-8e12-aee948d4bb1b)

<b/>

From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Username: root
Password: root

![image](https://github.com/user-attachments/assets/4af17c8f-39f7-4e5b-8f43-fcb450c93e68)


Open IIS as an Admin

Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

Reload IIS (Open IIS, Stop and Start the server)

![image](https://github.com/user-attachments/assets/6bbe6f40-5c8a-44a8-abad-2faff75895c1)


Install osTicket v1.15.8
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

![image](https://github.com/user-attachments/assets/d3c05ba3-217f-48a2-a223-078213a5b38f)

![image](https://github.com/user-attachments/assets/6a8a5a1d-f231-42d3-953f-f78785b56acb)


<b/>

Reload IIS (Open IIS, Stop and Start the server)

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

![image](https://github.com/user-attachments/assets/28330482-df97-4432-a356-bbdd6bac4428)

<b/>


Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browser, observe the changes

![image](https://github.com/user-attachments/assets/0cbfc114-f1e3-4dd0-86fa-59cb62bb6347)


Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

![image](https://github.com/user-attachments/assets/7c91d420-fc29-4723-b1fc-c2dfbf5c2a77)


Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

![image](https://github.com/user-attachments/assets/1124b6d0-84e9-4cea-ad62-04d5ffccb0c0)

![image](https://github.com/user-attachments/assets/708cd4d2-edac-486a-94e4-8128b7df4bb4)

Continue Setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)

From the “osTicket-Installation-Files” folder, install HeidiSQL.
Open Heidi SQL
Create a new session, root/root
Connect to the session
Create a database called “osTicket”

![image](https://github.com/user-attachments/assets/1c357c1e-68d1-450e-98d9-665393b1824f)


![image](https://github.com/user-attachments/assets/b559eaba-500b-4f9b-a7d1-5fc28239c7b0)


Continue Setting up osTicket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: root
Click “Install Now!”

![image](https://github.com/user-attachments/assets/e6a070da-e0d5-44c0-ae71-7e516b9d218c)


Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

![image](https://github.com/user-attachments/assets/677c1845-29ca-42c7-a30e-6fd46308f491)


  
</p>

