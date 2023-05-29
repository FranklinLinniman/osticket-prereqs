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

- Create a Microsoft Azure Virtual Machine
- Download and install PHP Manager for IIS 
- Download and install the Rewrite Module 
- Download PHP 7.3.8 
- Download and install VC_redist.x86.exe (c++ redistributable)
- Download and install MySQL 5.5.62
- Download and install HeidiSQL

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/Hh0Jweq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
1. Create an Azure Virtual Machine Windows 10, 4 vCPUs
 <br>
-Name: Vm-osticket
 <br>
-Username: labuser (for example/whatever you chose)
 <br>
-Password: osTicketPassword1! (for example/whatever you chose)

 
</p>
<br />

<p>
<img src="https://i.imgur.com/OatFozz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
2. Install / Enable IIS in Windows WITH CGI and Common HTTP Features
  <br>
-World Wide Web Services -> 
 <br>
- Application Development Features ->
 <br>
[X] CGI
 <br>
[X] Common HTTP Features
 
</p>
<br />

<p>
<img src="https://i.imgur.com/ERNq4Eu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
3. From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) 
</p>
<br />

                                                                                               
<img src="https://i.imgur.com/XmavXEe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/TzSlxCb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
4. From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)
 <br>
 -Create the directory C:\PHP
</p>
<br />

<img src="https://i.imgur.com/xQHxdMa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/HpidY8T.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
5. From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP  
</p>
<br />

<img src="https://i.imgur.com/26KvVLX.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
6. From the Installation Files, download and install VC_redist.x86.exe.   
</p>
<br />

<img src="https://i.imgur.com/lFBgJ06.png" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/bcvXOu5.png" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/c4VhTaX.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
7. From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
 <br>
-Typical Setup ->
 <br>
-Launch Configuration Wizard (after install) ->
 <br>
-Standard Configuration ->
 <br>
-Password1 (or whatever you want)
 </p>
<br />
 
 <img src="https://i.imgur.com/s4SxOhG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <img src="https://i.imgur.com/AYTII0v.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
8. Open IIS as an Admin
 <br>
-Register PHP from within IIS
 <br>
-Reload IIS (Open IIS, Stop and Start the server)
 </p>
<br />

 <img src="https://i.imgur.com/EaWnvuH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p> 
9. Install osTicket v1.15.8
 <br>
-Download osTicket from the Installation Files Folder
 <br>
-Extract and copy “upload” folder to c:\inetpub\wwwroot
 <br>
-Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”
 </p>
<br />

 
<img src="https://i.imgur.com/SeXltJt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
10.Reload IIS (Open IIS, Stop and Start the server)
 <br>
-Go to sites -> Default -> osTicket
 <br>
-On the right, click “Browse *:80”
 </p>
<br />

<img src="https://i.imgur.com/GPt20is.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <img src="https://i.imgur.com/K9bQs0x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 </p>
<p>
11. Note that some extensions are not enabled
 <br>
-Go back to IIS, sites -> Default -> osTicket
 <br>
-Double-click PHP Manager
 <br>
-Click “Enable or disable an extension”
 <br>
-Enable: php_imap.dll
 <br>
-Enable: php_intl.dll
 <br>
-Enable: php_opcache.dll
 <br>
-Refresh the osTicket site in your browser, observe the changes
 </p>
<br />

 </p>
<p>
12. Rename: ost-config.php
<br>
-From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
<br>
-To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
  </p>
<br />

 </p>
<p>
13. Assign Permissions: ost-config.php
 <br>
-Disable inheritance -> Remove All
 <br>
-New Permissions -> Everyone -> All
</p>
<br />
 
 </p>
<p>
14. Continue Setting up osTicket in the browser (click Continue)
 <br>
-Name Helpdesk
 <br>
-Default email (receives email from customers)
</p>
<br />

<img src="https://i.imgur.com/wkryG7F.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 </p>
<p>
15. From the Installation Files, download and install HeidiSQL.
 <br>
-Open Heidi SQL
 <br>
-Create a new session, root/Password1
 <br>
-Connect to the session
 <br>
-Create a database called “osTicket”
 </p>
<br />

<img src="https://i.imgur.com/LhYtc1h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 </p>
<p>
16. Continue Setting up osticket in the browser
<br>
-MySQL Database: osTicket
<br>
-MySQL Username: root
<br>
-MySQL Password: Password1
<br>
-Click “Install Now!”
 
 </p>
<p>
17. osTicket should be successfully installed with no errors!
 <br>
-Browse to your help desk login page: http://localhost/osTicket/scp/login.php 
</p>
<br />

<img src="https://i.imgur.com/CqpyarU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 </p>
<p>
18. Clean up
<br>
-Delete: C:\inetpub\wwwroot\osTicket\setup
<br>
-Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php

