Hi, I'm Jhon Louies, an "https://www.linkedin.com/in/jhon-louies-sanchez-6627a0284" IT Professional <h2> a Information Technology Projects:</h2>
- <b>osTicket (Help Desk Ticketing System)</b>
- [osTicket: Prerequisites and Installation](https://github.com/joshmadakorcc/osticket-preregs)
[osTicket: Post-Installation Configuration](https://github.com/joshmadakorcc/post-install-config)
- [osTicket: Ticket Lifecycle Examples](https://github.com/joshmadakorcc/ticket-lifecycle)
- <b›Microsoft Azures/b>
- [Configuring On-premises Active Directory within Azure VMs](https://github.com/joshmadakorcc/configure-ad)
- [Network Security Groups (N5Gs) and Inspecting Network Protocols](https://github.com/joshmadakorcc/azure-network-protocols)

<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket through Azure. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used</h2>

- Windows 10 (21H2)

<h2>List of Prerequisites</h2>

- Internet Information Services (IIS)
- Microsoft Web Platform Installer
- PHP Manager
- My SQL
- C++ 2008 Redistributable

<h2>Installation Steps</h2>

<p>
<img src="https://imgur.com/qXWOfvq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/egJMdgS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a "Virtual Machine" with Azure to run this lab. "Remote Desktop" into the created VM. 
</p>
<br />

<p>
<img src="https://imgur.com/n9ibcLa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install/Enable Internet "Internet Information Services" (IIS) in windows: control panel --> programs --> Turn Windows features on or off --> check box titled "Internet Information Services".  IIS is a windows server in which OsTicket requires to be enabled in order to run properly, even though OsTicket runs through the web browser.
</p>
<br />

<p>
<img src="https://imgur.com/YBPThz1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/OjPupsw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Search the internet for the installation files you will need to insatll. Find and install: "Web Platform Installer" & open "Web Platform Installer". Search Web Platform Installer to add "MySQL 5.5" & search to add all simple versions of PHP (x86) up until 7.3. "Create username" and "password" when asked to finish installation. Web installer will attempt to finish installing all of the prerequistes that are checked (some of the downloads will fail, just manually download C++ redistribuable & PHP Manager via files found online). Continue to finish with installation. Find and install "PHP Manager" version 7.3.8 & version 1.5.0. 
</p>
<br />

<p>
<img src="https://imgur.com/t2OkA7p.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Search the internet for "osTicket-v1.15.8" and download it. Next, copy the "upload folder" from inside the OsTicket installation files to "c:\inetpub\wwwroot". Within c:\inetput\wwwroot folder --> rename "upload folder" to "OsTicket" --> Open IIS--> osTicket--> Browse*80 --> restart IIS
</p>
<br />

<p>
<img src="https://imgur.com/KL5FPaL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Search and open "IIS program" again via windows search bar. Next, restart IIS server client for changes to take effect.  
</p>
<br />

<p>
<img src="https://imgur.com/AKPxXsc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After IIS restart --> select "OsTicket" within IIS under "Default Website" --> click Browse*:80. 
</p>
<br />

<p>
<img src="https://imgur.com/OdzWcn5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
If you have installed all prerequisites and followed all steps up to this point correctly, then the OS Ticketing system should open in the browser after the "browser*:80 port" is clicked in the previous step. 
</p>
<br />

<p>
<img src="https://imgur.com/kjIMvoQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/Yw6c5gd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click the "PHP Manager" option in ISS (If the option does not show then restart ISS) --> "Enable or disable an extension" --> enable the following extensins: "php_imap.dll, php_intl.dll, php_opcahe.dll" --> refresh OsTicket in the browser window.
</p>
<br />

<p>
<img src="https://imgur.com/e0Qis8c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/INrk5kt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Rename "C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php" to "C:\inetpub\wwwroot\osTicket\include\ost-config.php" --> Assign permissions: under security tab --> click advanced --> disable inheritance: remove all inheritance --> allow all permisions: click "add", select a "principal", enter "everyone" in object name field --> allow full control permissions. This will allow full control for everyone. 
</p>
<br />

<p>
<img src="https://imgur.com/4SxPW2u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After all previous steps are complete, the OsTicketing system should be fully functional and you should be allowed to create acual helpdesk tickets. Please see test ticket above. You have to fill out most, if not all, of the information for this setup. *The email address must be different for the system settings and the admin user to not create conflict. 
</p>
<br />

<p>
<img src="https://imgur.com/iecoXP0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install a program called "HeidiSQl" (can be searched online) that OsTicketing System uses to connect with Databases. Create a new "database" to be used with the new ticketing setup titled "OsTicket". Now, finish filling out the information in the OsTicket browser (MySQL will be the new database's name) and use whichever username and password that you created earlier in the lab. 












<!DOCTYPE html> 
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <i class="fa-envelope"</i>
    <p><a href="osTicket">osTicket: Prerequisites and Installation</a></p>
</head>
<body>
  
</body>
</html>

<p>
You should see a congratulations screen in the browser window if everything was done correctly. Clients are now able to successfully create help desk tickets. That concludes the lab.
</p>
<br />
</body>
</html>


