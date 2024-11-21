<p align="center">
<img src="https://i.imgur.com/hb8696w.png" alt="Proton VPN logo"/>
</p>

<h1>osTicket - Installation & Configuring</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Step 1: Create an Azure Virtual Machine Windows 10, 4 vCPUs
- Step 2: Log into the VM with Remote Desktop
- Step 3: Download osTicket Installation Files to VM
- Step 4: Install / Enable IIS in Windows WITH CGI
- Step 5: Install PHP Manager for IIS
- Step 6: Install the Rewrite Module
- Step 7: Create the directory C:\PHP
- Step 8: Install PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder
- Step 9: Install VC_redist.x86.exe
- Step 10: Install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
- Step 11: Open IIS as an Admin
- Step 12: Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)
- Step 13: Reload IIS (Open IIS, Stop and Start the server)
- Step 14: Install osTicket v1.15.8
- Step 15: Rename ost-config.php File
- Step 16: Continue setting up osTicket in Browser
- Step 17: Install HeidiSQL
- Step 18: 



<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/7E93uXW.png" height="80%" width="80%" alt=""/>
</p>
<p>
Step 1: Create an Azure Virtual Machine Windows 10, 4 vCPUs  
</p>

<p>
<img src="https://i.imgur.com/dlnWxf3.png" height="80%" width="80%" alt=""/>
</p>
<p>
Step 2: Log into the VM with Remote Desktop 
</p>

<p>
<img src="https://i.imgur.com/7E93uXW.png" height="80%" width="80%" alt=""/>
</p>
<p>
<h3> Step 3: Download osTicket Installation Files to VM </h3> 

We will use the files in this folder to install osTicket and some of the dependencies.   
</p>

<p>
<img src="https://i.imgur.com/UBjKqdS.png" height="80%" width="80%" alt=""/>
</p>
<p>
<h3>Step 4: Install / Enable IIS in Windows WITH CGI </h3> 

1. Go to start menu
2. Type in Control Panel
3. Click Uninstall Programs
4. Click Turn Windows Features On and Off
5. Tick Internet Information Services > World Wide Web Services > Application Development Features > CGI
6. Click OK

You can now enter 'http://127.0.0.1/' and it should return a splash screen for IIS. 
</p>

<p>
<img src="https://i.imgur.com/Fggqsfc.png" height="80%" width="80%" alt=""/>
</p>
<p>
<h3>Step 5: Step 5: Install PHP Manager for IIS</h3>

From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)  
</p>
<p>
<img src="https://i.imgur.com/XFUaltz.png" height="80%" width="80%" alt=""/>
</p>

<p>
<h3>Step 6: Install the Rewrite Module</h3>
</p>
<p>
<img src="https://i.imgur.com/RwacG67.png" height="80%" width="80%" alt=""/>
</p>

<p>
<h3>Step 7: Create the directory C:\PHP</h3>

1. Right-click the manila folder on the taskbar
2. Choose File Explorer
3. Click the chevron for This PC
4. Click Windows (C:)
5. Right-click and choose New Folder
6. Rename the folder PHP  
</p>
<p>
<img src="https://i.imgur.com/DkY0y1h.png" height="80%" width="80%" alt=""/>
</p>

<p>
<h3>Step 8: Install PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder</h3>
</p>
<p>
<img src="https://i.imgur.com/b9hlgqC.png" height="80%" width="80%" alt=""/>
</p>

<p>
<h3>Step 9: Install VC_redist.x86.exe</h3>
</p>
<p>
<img src="https://i.imgur.com/5xCSTHQ.png" height="80%" width="80%" alt=""/>
</p>

<h3>Step 10: Step 10: Install MySQL 5.5.62 (mysql-5.5.62-win32.msi) </h3>

- Typical Setup ->
- Launch Configuration Wizard (after install) ->
- Standard Configuration ->
- Username: root
- Password: root

<p>
<img src="https://i.imgur.com/bn4PNDX.png" height="80%" width="80%" alt=""/>
</p>
<p>
<h3>Step 11: Open IIS as an Admin </h3>
</p>
<p>
<img src="https://i.imgur.com/yeFYtWs.png" height="80%" width="80%" alt=""/>
</p>

<p>
<h3>Step 12: Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)</h3>
</p>
<p>
<img src="https://i.imgur.com/IJy7kNT.png" height="80%" width="80%" alt=""/>
</p>

<p>
<h3>Step 13: Reload IIS (Open IIS, Stop and Start the server)</h3>
</p>
<p>
<img src="https://i.imgur.com/fTAIcTx.png" height="80%" width="80%" alt=""/>
</p>

<h3>Step 14: Install osTicket v1.15.8</h3>
<p>
1. From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”. <br>
2. Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket” 
3. Reload IIS (Open IIS, Stop and Start the server)
</p>
<p>
<img src="https://i.imgur.com/MarKOex.png" height="80%" width="80%" alt=""/>
</p>

<h3>Go to sites -> Default -> osTicket</h3>
<p>
On the right, click “Browse *:80” <br />

- Note that some extensions are not enabled
  - Go back to IIS, sites -> Default -> osTicket
  - Double-click PHP Manager
  - Click “Enable or disable an extension”
  - Enable: php_imap.dll
  - Enable: php_intl.dll
  - Enable: php_opcache.dll
  - Refresh the osTicket site in your browser, observe the changes

<p>
<img src="https://i.imgur.com/OgdAQF2.png" height="80%" width="80%" alt=""/>
</p>

<h3>Step 15: Rename: ost-config.php</h3>
<p>
1. From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”. <br>
2. Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket” 
3. Reload IIS (Open IIS, Stop and Start the server)
</p>
<p>
<img src="https://i.imgur.com/MarKOex.png" height="80%" width="80%" alt=""/>
</p>

<h3>Step 15: Rename: ost-config.php</h3>

<p>
Rename ost-config.php from: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
<p>
<img src="https://i.imgur.com/smksfV2.png" height="80%" width="80%" alt=""/>
</p>

<h3>Step 16: Assign permissions</h3>

<p>
Assign Permissions: ost-config.php </br>
Disable inheritance -> Remove All </br>
New Permissions -> Everyone -> All </br>
</p>
<p>
<img src="https://i.imgur.com/JTMxcXa.png" height="80%" width="80%" alt=""/>
</p>

<h3>Step 16: Continue setting up osTicket in Browser</h3>

<p>
1. Continue Setting up osTicket in the browser (click Continue) </br>
2. Name Helpdesk </br>
3. Default email (receives email from customers) 
</p>
<p>
<img src="https://i.imgur.com/FUwZPbS.png" height="80%" width="80%" alt=""/>
</p>

<h3>Step 17: Install HeidiSQL</h3>

<p>
1. Open Heidi SQL </br>
2. Create a new session, root/root </br>
3. Connect to the session </br>
4. Right-click Unamed > Create New > Database </br>
5. Name the new database “osTicket” </br>

</p>
<p>
<img src="https://i.imgur.com/mjquXsh.png" height="80%" width="80%" alt=""/>
</p>

<h3>Step 18: Continue setting up osTicket in Browser</h3>

<p>
1. MySQL Database: osTicket </br>
2. MySQL Username: root </br>
3. MySQL Password: root </br>
4. Click “Install Now!” 
</p>
<p>
<img src="https://i.imgur.com/q2MQT3p.png" height="80%" width="80%" alt=""/>
</p>
