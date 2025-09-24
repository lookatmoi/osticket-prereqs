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

- Create an Azure Virtual Machine Windows 10, 4 vCPUs
- Log into the VM with Remote Desktop
- Install / Enable IIS in Windows WITH CGI
- Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)
- Use a browser to complete the osTicket setup

<h2>Installation Steps</h2>

<img width="1507" height="796" alt="image" src="https://github.com/user-attachments/assets/147b3870-c9b3-4941-8501-a83521f683e5" />

- Create an Azure Virtual Machine Windows 10, 4 vCPUs

- Log into the VM with Remote Desktop
-Within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip it onto your desktop. The folder should be called “osTicket-Installation-Files”
We will use the files in this folder to install osTicket and some of the dependencies.

-Install / Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI

-From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

-From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

-Create the directory C:\PHP

-From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

-From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

-From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->

Open IIS as an Admin

Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

Reload IIS (Open IIS, Stop and Start the server)

<img width="1429" height="736" alt="image" src="https://github.com/user-attachments/assets/2d07870d-a28f-488b-a7a7-8c596d354549" />
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Install osTicket v1.15.8

From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)

<img width="1906" height="1033" alt="image" src="https://github.com/user-attachments/assets/9e3be20d-33f5-41dc-b1fd-0230615abf4f" />

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browser, observe the changes

Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

Continue Setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)

From the “osTicket-Installation-Files” folder, install HeidiSQL.
Open Heidi SQL
Create a new session, root/root
Connect to the session
Create a database called “osTicket”
<img width="946" height="595" alt="image" src="https://github.com/user-attachments/assets/7f028191-4141-4001-975d-ee6ed17d345a" />

Continue Setting up osTicket in the browser
MySQL Database: osTicket
MySQL Username: TBD
MySQL Password: TBD
Click “Install Now!”
<img width="1900" height="964" alt="image" src="https://github.com/user-attachments/assets/a1398b15-ea77-4f07-8012-76819ab58eb2" />


</p>
<br />

<p>
</p>
<p>
 
</p>
<br />

<p>

</p>
<p>

</p>
<br />
