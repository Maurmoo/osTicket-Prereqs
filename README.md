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
- Step 4: Install All Dependencies
- Step 5: Configure IIS and PHP
- Step 6: Install and ConfiosTicketgure
- Step 7: Enable PHP Extensions
- Step 8: Configure osTicket
- Step 9: Set Up the Database
- Step 10: Finalize osTicket Installation
<h2>Installation Steps</h2>

<p>
  
  ## Step 1: Create and Configure the Azure VM
  
![image](https://github.com/user-attachments/assets/c33e733e-903c-4ce8-bc5c-f012f1209d7f)

</p>
<p>
  
- Created a Windows 10 Virtual Machine on Azure with the following specifications
- Name: **Ticket**
- vCPUs: **4**
- Username: **Labuser**
- Password: **Password1234**
- Logged into the VM using Remote Desktop. IP address: **20.106.188.26**
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

## Step 4: Install All Dependencies
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

## Step 5: Configure IIS and PHP
## Opened IIS Manager as Administrator
![image](https://github.com/user-attachments/assets/0b36eb19-cf79-4e96-8601-5dbf9dab6022)
</p>
<p>
  
- Opened IIS Manager as Administrator.

</p>
<br />

## Register PHP, Reload IIS
![image](https://github.com/user-attachments/assets/f7e7a652-c910-41ab-84af-15435a09037e)
![image](https://github.com/user-attachments/assets/853039fb-f95d-4a19-98e1-1aa85736a1cc)
</p>
<p>
  
- In IIS, go to PHP Manager / Select Register PHP.
- Provide the path: C:\PHP\php-cgi.exe.
- Go back to osTicket home
- Stop and start the IIS server.

</p>
<br />

## Step 6: Install and ConfiosTicketgure 
## Deploy osTicket Files
![image](https://github.com/user-attachments/assets/46300533-5c07-4cf2-8443-4fdb9475aaff)

</p>
<p>
  
- From the osTicket-Installation-Files folder, unzip osTicket-v1.15.8.zip.
- Copy the upload folder to C:\inetpub\wwwroot.
- Rename the folder from upload to osTicket.
- Reload IIS Stop and start the IIS server.
</p>
<br />

## Access osTicket
![image](https://github.com/user-attachments/assets/bebb164e-c76e-4002-abd7-6fb04d584242)
</p>
<p>
  
- In IIS, navigate to Sites → Default Web Site → osTicket.
- On the right, click *Browse:80 to open osTicket in the browser.
</p>
<br />

## Step 7: Enable PHP Extensions
## PHP extensions
![image](https://github.com/user-attachments/assets/e1fe43d7-32ec-4c45-a877-cb8436da835e)

</p>
<p>


- In IIS, go to Sites → Default Web Site → osTicket → PHP Manager.
- Click Enable or disable an extension and enable:
- php_imap.dll
- php_intl.dll
- php_opcache.dll
</p>
<br />

## Refresh Page
![image](https://github.com/user-attachments/assets/14896e69-a47b-4138-b108-7417f68262c9)
</p>
<p>

- Refresh the osTicket site in the browser to observe the changes.
</p>
<br />

## Step 8: Configure osTicket
## Rename the Configuration File
![image](https://github.com/user-attachments/assets/a8e9e534-66c1-421b-bce1-40673a33a916)
</p>
<p>
  
- Rename C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to ost-config.php.

</p>
<br />

##  Setting Permissions to everyone on ost-config.php
![image](https://github.com/user-attachments/assets/11cda075-f4de-4025-b5a7-f6e27715b245)
</p>
<p>

- Right-click on the file and select Properties.
- Navigate to the Security tab and click on Advanced.
- In the Advanced Security Settings window: Click Disable Inheritance (if inheritance is enabled).
- When prompted, choose Remove all inherited permissions.
- Click Add to set new permissions.
- In the Permission Entry window:
- Click Select a Principal.
- In the Enter the object name field, type Everyone and click OK.
- Back in the Permission Entry window:
- Under Basic Permissions, check the box for Full Control.
- Click OK to confirm.
- Click Apply and then OK to finalize the changes.
</p>
<br />

## Step 9: Setup Database
![image](https://github.com/user-attachments/assets/04f68133-0b44-41f3-8dc2-9443d575a765)
</p>
<p>

- Open HeidiSQL and create a new session (root/root).
- Right-click "unnamed" Create new / Database
- Named "osTicket" Then click ok
</p>
<br />

## Step 10: Finalize osTicket Installation
## Information
![image](https://github.com/user-attachments/assets/77ed3d05-9288-4e2e-82e6-cee3312fd0d7)

</p>
<p>
- Go back to osTicket webpage
- Click Continue
- Fill out all information till you reach Database Settings
</p>
<br />

## Set MySQL database details
![image](https://github.com/user-attachments/assets/33579309-2cb4-44cb-83e8-4ca657163906)
</p>
<p>
  
- In the browser Set MySQL database details:
- Database: osTicket
- Username: root
- Password: root
- Click Install Now!
- Verify the installation at:
- Admin Login: http://localhost/osTicket/scp/login.php
- End-User Portal: http://localhost/osTicket/
</p>
<br />

## Installation Finished
![image](https://github.com/user-attachments/assets/9e711ecc-cf87-4164-ac27-cdc44c71ff3f)

## Verify the installation 
![image](https://github.com/user-attachments/assets/c099fd1e-9bad-4546-9a0c-38898dd7acf9)
</p>
<p>
  
Admin Login: http://localhost/osTicket/scp/login.php
End-User Portal: http://localhost/osTicket/
</p>
<be />

## Conclusion
In conclusion, installing osTicket on a Windows 10 virtual machine in Azure involves configuring IIS, PHP, and MySQL, along with deploying the osTicket files. By following the installation steps, you ensure that the help desk system is ready for use, offering an efficient ticketing solution for managing incidents and improving support workflows. This setup provides a streamlined platform for both admins and end-users, enhancing overall customer service and operational efficiency.

![Azure](https://img.shields.io/badge/Azure-Cloud-blue)

