# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial will outline the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

Before proceeding with the installation of osTicket, ensure the following prerequisites have been met:

1. Azure Virtual Machine Setup:
- Create an Azure Virtual Machine with the following specifications:
     - Windows 10
     - 4 vCPUs

2. IIS and Features Configuration:
- Inside the Azure Virtual Machine:
     - Open the Control Panel.
     - Navigate to "Programs" > "Programs and Features" > "Turn Windows features on or off."
     - Enable the following features:
          - Internet Information Services (IIS)
          - CGI
          - Common HTTP Features
          - IIS Management Console

3. Verification:
- Open a web browser within the Azure Virtual Machine.
- Enter "http://127.0.0.1" to confirm that Internet Information Services (IIS) is installed and operational. You should see the default IIS page.

4. PHP and Rewrite Module Installation:
- Inside the Azure Virtual Machine:
     - Install "PHP Manager for IIS" and the "URL Rewrite Module" using the provided installers.

5. Directory and PHP Configuration:
- Inside the Azure Virtual Machine:
     - Create a directory at "C:\PHP."
     - Download PHP 7.3.8 for Windows, and extract its contents into "C:\PHP."

6. VC_redist.x86.exe Installation:
- Inside the Azure Virtual Machine:
     - Install "VC_redist.x86.exe" to ensure PHP compatibility.

7. MySQL Installation:
- Inside the Azure Virtual Machine:
     - Install MySQL 5.5.62 for Windows using the provided installer.

Once all these prerequisites are completed, you can proceed with the installation of osTicket, knowing that the required environment is properly configured and ready for use.

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Open IIS as an Admin
  - Search for "Internet Information Services (IIS)" in your Windows search bar.
Right-click on the result and select "Run as administrator" to open IIS with administrative privileges.
  
- Register PHP from within IIS
     - Within IIS, find and select the "PHP Manager."
Click on it to open the PHP Manager.
Click on Register new PHP version. Click and Browse This PC. Navigate to C drive ( Windows (C))\ PHP\php-cgi.
Click okay

- Reload IIS (Open IIS, Stop and Start the server)
     - To reload IIS, stop and start the server.
In IIS, right-click on your server (usually listed on the left side).
Choose "Stop" to stop the server.
Then, right-click again and select "Start" to start the server.

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Install osTicket v1.15.8
  
  - Download osTicket.
       - Extract the downloaded file.
Copy the "upload" folder to your C drive (C:\inetpub\wwwroot).
After copying, rename the "upload" folder to "osTicket."

- Reload IIS (Open IIS, Stop and Start the server)
     - Follow the same steps as in step 3 to stop and start the IIS server.
   
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

- Access osTicket  
     - In IIS, go to "sites" and find "Default." Look for the "osTicket" option. On the right side, click "Browse *:80" to access osTicket.

- Enable PHP Extensions
    - In IIS, find "Default" and "osTicket" again.
Double-click "PHP Manager."
Click "Enable or disable an extension."
         - Enable the following extensions:
           
           php_imap.dll

           php_intl.dll

           php_opcache.dll
           
- After enabling these extensions, refresh the osTicket site in your web browser to see the changes.

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

- Rename Configuration File
     - Navigate to C:\inetpub\wwwroot\osTicket\include.
Find a file named "ost-sampleconfig.php."
Rename it to "ost-config.php."
    
 - Assign Permissions to ost-config.php
      - Right-click on the "ost-config.php" file.
Choose "Properties."
In the "Security" tab, click "Edit" to change permissions.
Disable inheritance and remove all existing permissions.
Add a new permission for "Everyone" with "Full Control."

- Continue Setting up osTicket in the Browser
     - Open your web browser and visit the osTicket site (should be at http://localhost/osTicket).
- Follow on-screen instructions to set up your helpdesk.
- Provide a name for your helpdesk and a default email address for receiving customer emails.

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

- Install HeidiSQL:
     - Download and Install HeidiSQL on your computer.
  
  - Open HeidiSQL and Create a Database
       - Open HeidiSQL.
       - Create a new session with the following information:
       - Username: root
       - Password: Password1
       - Connect to the session.
       - Create a new database called "osTicket."
  

- Continue Setting up osTicket in the Browser
     - Go back to your web browser where you were setting up osTicket.
     - Provide the following MySQL database information:
     - Database Name: osTicket
     - MySQL Username: root
     - MySQL Password: Password1
     - Click "Install Now!"

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

- Your osTicket should now be installed without errors.
- To access your helpdesk login page, go to: http://localhost/osTicket/scp/login.php.

That's it! You've successfully set up osTicket on your system.


















































































































