<img src="https://iili.io/dGyagHX.png">
<hr align="left" height="99%" width="99%"></hr>
 <h2>osTicket--Prerequisites-and-Installation</h2>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.

<h3>Video Demonstration</h3>
<ul>
    <li><a href="https://www.youtube.com/watch?v=fWX1Lj-rOa0">YouTube: How to Install osTicket with Prerequisites</a></li>
</ul>
<hr align="left" height="99%" width="99%"></hr>
<h3>Environments and Technologies Used</h3>
<ul>
   <li>Microsoft Azure (Virtual Machines/Compute)</li>
   <li>Remote Desktop</li>
   <li>Internet Information Services (IIS)</li> 
</ul>
<hr height="99%" width="99%"></hr>
<h3>Operating Systems Used</h3>
<ul>
   <li>Windows 10 (21H2)</li>
</ul>
<hr align="left" height="99%" width="99%"></hr>
<h3>List of Prerequisites</h3>
<ul>
   <li>Microsoft Azure</li>
   <li>Virtual Machine</li>
   <li>osTicket Installation Files</li>

</ul>
<hr align="left" height="99%" width="99%"></hr>
<h3>Installation Steps</h3>
<p>
Open https://portal.azure.com
<br>Sign in to your Azure account
<br>Under the section Create a Resource Group, in Resource group* called RG-bv-osTicket
<br>Select Region*, to (Canada) Canada Central
<br>Click Review + Create, if Validation passed, Click Create. 
<br>In the search box, type in virtual machine. 
<br>
<br>
<img src="https://iili.io/dM25uIe.png" height="80%" width="80%" alt="screenshot1">

In Virtual machines, click + Create
<br>Under Project details, in Resource group*, select RG-bv-osTicket
<br>Under Instance details, in Virtual machine name*, type VM-osTicket
<br>In region*, Select (Canada) Canada Central
<br>In Image*, Select Windows 10 Pro version 22H2 - x64 Gen2 (free services eligible)
<br>In size*, select Standard_D4s_v3 - 4 vcpus, 16 GiB memory ($162.06/month)
<br>
<br>
<img src="https://iili.io/dM3FCaj.png" height="96%" width="96%" alt="screenshot2">

<br>
<br>
<img src="https://iili.io/dM3qUoN.png" height="96%" width="96%" alt="screenshot3">

In Administrator account:
<br>In username*, type bv-labuser
<br>In password*, type #Bv-12345678
<br>In Confirm password*, type #Bv-12345678

In Licensing:
<br>Check the box for "I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights".
<br>Click Next for Disks. Click next for Networking. 

In Networking:
<br>Click Review + Create. If Validation passed, Click Create. 

<br>
<br>
<img src="https://iili.io/dM3VhSn.png" height="96%" width="96%" alt="screenshot3">

Your Virtual Machine deployment is successful! 

<br>
<hr align="left" height="99%" width="99%"></hr> 


Reference: https://docs.google.com/document/d/12QH7yrsaiUfYNOgZK7KgTSZQSJ-HYTSVcGFildWMRig/edit
<br>
<h3>Installation video:</h3>
<br>In Virtual machines, click your VM-osTicket name
<br>For windows users, click start menu by typing "Remote desktop connection" app. 
<br>Copy and paste your VM Public IP address to Computer:
<br>Click Connect
<br>Enter your credentials, user name and password. 
<br>The identity of the remote computer cannot be verified. Do you want to connect anyway? box appears. Click Yes. 
<br>
<br>For Mac users, you need to install "Microsoft Remote Desktop" from the App Store. 
<br>clicking magnify icon on top right of Chrome or Command + space, click + add PC
<br>Copy and Paste your VM Public IP address in to PC name: 
<br>
<br>Start menu, click run, type control panel
<br>click programs, click Turn windows features on or off
<br>
<br>Install / Enable IIS in Windows WITH
<br>CGI and Common HTTP Features
<br>World Wide Web Services -> Application Development Features ->
<br>[X] CGI
<br>[X] Common HTTP Features
<br>Make sure all folders in Common HTTP Features are check marked, 
<br>There should be 6 folders. 
<br>click ok. 
<br>Windows completed the requested changes. click close. 
<br>
<br>Note: IIS is a web server that osTicket runs on
<br>
<br>open a new tab window, type in the URL box, 127.0.0.1 for Internet Information Services web page to load. 
<br>Note: If URL 127.0.0.1 web page did not load, go to control panel
<br>click uninstall a program, click turn windows feature on or off
<br>uncheck box in Internet Information Services, then do the installation again. 
<br>
From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)

Create the directory C:\PHP
-Create a folder called PHP in Drive C

From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
!! ATTENTION !!
If this appears, choose to “Keep” the file:

From the Installation Files, download and install VC_redist.x86.exe.
From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
-Typical Setup ->
-Launch Configuration Wizard (after install) ->
-Standard Configuration ->
mysql login:
-username: root
-Password: Password1

Open IIS as an Administrator
-start menu, type IIS (Internet Information Services Manager App)
-right click as run as Administrator
Register PHP from within IIS
-In IIS, click PHP Manager
-click register new PHP version
Reload IIS (Open IIS, Stop and Start the server)
-Make sure VM-osTicket is selected, under manage server, click restart
Install osTicket v1.15.8
-Download osTicket from the Installation Files Folder
-Extract and copy “upload” folder to c:\inetpub\wwwroot
-Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)
-Make sure VM-osTicket is selected, under manage server, click restart
Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

Note that some extensions are not enabled
-Go back to IIS, sites -> Default -> osTicket
-Double-click PHP Manager
-Click “Enable or disable an extension”
-Enable: php_imap.dll
-Enable: php_intl.dll
-Enable: php_opcache.dll
-Refresh the osTicket site in your browse, observe the changes

Rename: ost-config.php
-From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
-To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
-Disable inheritance -> Remove All
-New Permissions -> Everyone -> All

Continue Setting up osTicket in the browser (click Continue)
-Name Helpdesk
-Default email (receives email from customers)

Helpdesk name: Boby Help Desk
Default email: bvilayvong@hotmail.com
First Name: Boby
Last Name: Vilayvong
Email Address: bvilayvong@hotmail.com
Username: bvilayvong
Password: Password1


From the Installation Files, download and install HeidiSQL.
-Open Heidi SQL
-Create a new session, root/Password1
-Connect to the session
-Create a database called “osTicket”

Continue Setting up osticket in the browser
-MySQL Database: osTicket
-MySQL Username: root
-MySQL Password: Password1
-Click “Install Now!”

Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php
For admin logins to do admin things. 

End Users osTicket URL: for creating tickets
http://localhost/osTicket/ 

Clean up
Delete: C:\inetpub\wwwroot\osTicket\setup
Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Notes:
Browse to your help desk login page: http://localhost/osTicket/scp/login.php  
End Users osTicket URL: http://localhost/osTicket/ 



<br>
<br>
</p>





<p>
Step 1: Connect to your Virtual Machine with Remote Desktop

Step 2: Install and Enable Internet Services (IIS) in Windows

Placeholder image
<img src="" height="80%" width="80%" alt="Disk Sanitization steps">
Lorem ipsum....
</p>
<p>
Placeholder image
<img src="">
Lorem ipsum....
</p>
<p>
Placeholder image
<img src="">
Lorem ipsum....
</p>



