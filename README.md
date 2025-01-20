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

- Step 1: Create and Configure the Azure VM
- Step 2: Download osTicket Installation Files
- Step 3: Enable IIS and CGI in Windows
- Step 4: Install Required Components
- Step 5: Configure IIS
- Step 6: Install osTicket
- Step 7: Enable PHP Extensions
- Step 8: Configure osTicket
- Step 9: Set Up the Database
- Step 10: Finalize Installation
<h2>Installation Steps</h2>

<p>
  
  ## Step 1: Create and Configure the Azure VM
  
![image](https://github.com/user-attachments/assets/c33e733e-903c-4ce8-bc5c-f012f1209d7f)

</p>
<p>
  
- Created a Windows 10 Virtual Machine on Azure with the following specifications:
- Name: Ticket
- vCPUs: 4
- Username: Labuser
- Password: Password1234
- Logged into the VM using Remote Desktop. IP address: 20.106.188.26
</p>
<br />

<p>
  
## Step 2: Download Installation Files
  
![image](https://github.com/user-attachments/assets/c8652e6f-0351-471e-a05b-d6a0bc6e5fc3)

</p>
<p>
  
- Downloaded the osTicket-Installation-Files.zip into the Virtual machine.
  
- osTicket Installation Files link: https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
  
</p>
<br />

## Step 3: Enable IIS and CGI in Windows 

<p>
 
![image](https://github.com/user-attachments/assets/ad071228-111e-4a9d-8e12-13defa3d2ca7)

</p>
<p>
  
- Open Control Panel / Programs / Turn Windows features on or off.
- Expand World Wide Web Services / Application Development Features.
- Check the box for CGI and click OK.

</p>
<br />

## Step 3: Install All Dependencies
## PHPmanager
![image](https://github.com/user-attachments/assets/34ad9eba-d195-48a0-a046-0d09605fa6b9)

</p>
<p>
  
- From the osTicket-Installation-Files folder, Install PHPManagerForIIS_V1.5.0.msi.
## Rewrite_amd  
![image](https://github.com/user-attachments/assets/928f45e9-103a-4448-a8ee-6e9588471f6f)

- From the same folder, Install rewrite_amd64_en-US.msi.

</p>
<br />

## PHP folder
![image](https://github.com/user-attachments/assets/ec88a5f6-1e14-4236-be60-59cb7a04b187)

</p>
<p>
  
- Created the directory C:\PHP.
  
</p>
<br />

## Extract PHP
![image](https://github.com/user-attachments/assets/ada5d48e-09a5-4125-be79-3ffb0171cf31)

</p>
<p>
  

- Unziped php-7.3.8-nts-Win32-VC15-x86.zip from the osTicket-Installation-Files folder into C:\PHP.

</p>
<br />

## VC_redist
![image](https://github.com/user-attachments/assets/100482cf-c9c4-4832-9d32-9413d3ae4c13)

</p>
<p>
  
- From the folder, Install VC_redist.x86.exe.

</p>
<br />

## MYSQL
![image](https://github.com/user-attachments/assets/50034a01-1550-4585-a83c-8f5bd0cf955b)

</p>
<p>
  
- From the folder, Install mysql-5.5.62-win32.msi.
- Select Typical Setup.
- Launch the Configuration Wizard after installation.
- Use Standard Configuration and set:
- Username: root
- Password: root.

</p>
<br />

## HeidiSQL
![image](https://github.com/user-attachments/assets/b32d179c-88f3-45fd-88ca-8c583014c1e2)

</p>
<p>
  
- From the folder, Install the HeidiSQL installer.

</p>
<br />

## Step 4: Configure IIS and PHP
![image](https://github.com/user-attachments/assets/0b36eb19-cf79-4e96-8601-5dbf9dab6022)
</p>
<p>
  
- Opened IIS Manager as Administrator.

</p>
<br />

![image](https://github.com/user-attachments/assets/f7e7a652-c910-41ab-84af-15435a09037e)
![image](https://github.com/user-attachments/assets/853039fb-f95d-4a19-98e1-1aa85736a1cc)
</p>
<p>
  
- Registered PHP:
- In IIS, go to PHP Manager / Select Register PHP.
- Provide the path: C:\PHP\php-cgi.exe.
- Go back to osTicket home
- Stop and start the IIS server.

</p>
<br />

## Credits
This Project is based on the template by Josh Madakor. I've customized it to suit my needs while retaining the structure and inspiration from the original work.
https://github.com/joshmadakorcc/post-install-config
