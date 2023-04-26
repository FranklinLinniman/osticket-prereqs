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

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/tay8Mrd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here we have created a virtual machine in Microsoft Azure that is running 4 virtual CPU's. You can create your own resource group, or one will be created for you automatically after you have created your virtual machine. Once we have created our virtual machine, we will connect to it via Remote Desktop protocol. We will use this virtual machine for the initial installation of osTicket and to run osTicket in future labs.
 
</p>
<br />

<p>
<img src="https://i.imgur.com/AKX1KTq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Be sure to enable IIS with CGI, if you forget to enable CGI you will not be able to run PHP (back end software that osTicket runs off of). Use a provided link to download and install PHP manager. Follow the Installation guide and install PHP manager. 
</p>
<br />

<p>
<img src="https://i.imgur.com/QsPqguZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and install the rewrite module by following the installation guide 
</p>
<br />

                                                                                               
<img src="https://i.imgur.com/6654vbE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a directory for PHP on the root of C: drive. Then, download PHP using a provided link and unzip the contents into the PHP folder on C: drive.  
</p>
<br />

<img src="https://i.imgur.com/6654vbE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and install c++ redistributable using a provided link.   
</p>
<br />

<img src="https://i.imgur.com/L9MWwTq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and install My SQL using a provided link.My SQL is a database that will be used by osTicket to store users, tickets, etc.    
</p>
<br />

</p>
<p>
Open IIS as an Admin

Register PHP from within IIS

Reload IIS (Open IIS, Stop and Start the server)

Install osTicket v1.15.8
Download osTicket from the Installation Files Folder,
Extract and copy “upload” folder to c:\inetpub\wwwroot,
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager,
Click “Enable or disable an extension”,
Enable: php_imap.dll,
Enable: php_intl.dll,
Enable: php_opcache.dll,
Refresh the osTicket site in your browser, observe the changes

Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php,
Disable inheritance -> Remove All,
New Permissions -> Everyone -> All

Continue Setting up osTicket in the browser (click Continue),
Name Helpdesk,
Default email (receives email from customers)

</p>
<br />
