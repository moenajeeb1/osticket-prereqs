<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial touches on the prerequisites and installation of the help desk ticketing system osTicket!<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- osTicket Installation files
- Heidi SQL

<h2>Installation Steps</h2>

<p>
</p>
<p>
Greetings and welcome to my first tutorial of many! The first thing to do is to create a virtual machine in the Microsoft Azure Portal. We'll use a virtual machine that is a remote computer essentially. Create a resource group and title it anything you'd like. I personally named my resource group "RG-LAB02" Then we will create a virtual machine with 2-4 CPUs. I personally chose a VM with two CPUs. When creating the VM, allow it to create a Virtual Network (Vnet) </p>
  
<img src="https://i.imgur.com/SaGJWwR.png" height="80%" width="80%"/>
 <img src="https://i.imgur.com/x3Nr0P7.png" height="80%" width="80%"/>
</p>
<br />
<p>
</p>
<p>Now we will connect to the Virtual Machine using remote desktop. We connect by using the public IPv4 address. You can copy and paste it by clicking on the VM's info. Mac users like myself will have to download Microsoft RDP and connect through there. 
</p>
<img src="https://i.imgur.com/1ByH8Uh.png" height="80%" width="80%"/>
</p>
<br />

<p>
</p>
<p>
We are now successfully in and connected to our VM. We now have to install and enable IIS with CGI. Locate and enter the control panel inside your VM and click on programs. Click on turn Windows feautures on or off. Then click on Internet Information Services, World Wide Web Services, Application Development Features, and last CGI. 
</p>  
<img src="https://i.imgur.com/go3XhXN.jpg" height="80%" width="80%"/>
</p>
<br />
</p>
<p>
We have successfully enabled IIS within our VM and now there are a series of programs and files we have to install and run. https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6 is the link of all the files we will need to install and run to have osTicket in our system working and running. Download and install PHP Manager for IIS through the link that has been provided. 
  
</p>
<img src="https://i.imgur.com/rw4auoC.jpg" height="80%" width="80%"/>  
</p>
<p>
From the installation files, go ahead and download the rest of the programs given through the link we downloaded our PHP Manager from. Then create the directory C:\PHP and unzip PHP 7.3.8 contents into there.
</p>
<img src="https://i.imgur.com/N5bUybD.jpg" height="80%" width="80%"/>
<p>
</p>
<p>
After installing MySQL 5.5.62, click and launch a typical setup configuration then open IIS as an admin and register PHP from within IIS.
</P>
<img src="https://i.imgur.com/sVaE5SO.jpg" height="80%" width="80%"/>
</p>
<br />
<p>
</p>
<p>
Download osTicket from the Installation Files Folder. Then
extract and copy “upload” folder to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot. Rename “upload” to “osTicket”

</p>
<img src="https://i.imgur.com/ouWGaIY.jpg" height="80%" width="80%"/>
<br />
<p>
</p>
<p>
Notice that some extensions are not enabled. To enable them you have to go back to IIS, sites -> Default -> osTicket and double click the PHP manager.
 Click on enable or disable an extension. Proceed to enable "php_intl.dll", "php_opcache.dll" , and "php_imap.dll and refresh the osTicket in your browser and observe the changes.
</p>
<img src="https://i.imgur.com/RwrxiYT.jpg" height="80%" width="80%"/>
<br />
<p>
</p>
<p>
From: C:\inetpub\wwwroot\osTicket\include rename ost-sampleconfig.php to ost-config.php. Assign the permissions of ost-config.php Disable inheritance -> Remove All and New Permissions -> Everyone -> All


  
</p>
<img src="https://i.imgur.com/EauQzkJ.jpg" height="80%" width="80%"/>
<br />
<p>
</p>
<p>
Continue setting up osTicket in the browser (click continue) Create your own help desk name of your choice. Put a default email (receive emails from customers submitting tickets.) 
</p>
<img src="https://i.imgur.com/DotKKqR.jpg" height="80%" width="80%"/>
<br />
<p>
<p>Continue setting up osticket in the browser and download and install HeidiSQL open and create new session. Connect to the session and create a new database. MySQL Database: osTicket MySQL Username: root MySQL Password: Password1 then proceed to click install now.
Congratulations and hopefully it is installed with no errors!
Clean up
Delete: C:\inetpub\wwwroot\osTicket\setup
Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
Login to the osTicket Admin Panel (http://localhost/osTicket/scp/login.php)

