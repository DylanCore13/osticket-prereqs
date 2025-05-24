# osTicket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

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
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
