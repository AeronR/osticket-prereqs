<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

In this document I will be demonstrating how to create a osTicketing system from scratch with the use of Azure Virtual Machines

Benefits of knowing the ticketing system:

1.) Organization and prioritization of requests.

2.) Centralized communication between users and the IT team.

3.) Improves tracking and accountability.

4.) Enhanced collaboration within the IT team.

5.) Compliance with Service Level Agreements (SLAs).

6.) Creation of knwoledge base for self-service.

7.) Increase customer satisfaction. 


<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Internet Information Services(IIS)
- MySQL 5.5
- Simple versions of x86 PHP up to 7.3
- osTicket v1.15.8

<h2>Installation Steps</h2>

<p>
 
First things first, I created a Windows 10 Virtual Machine through Azure. 

<sub>***These installation steps do not include how to create a Virtual Machine***</sub>
  
The following images are through the Windows VM already.

</p>

<p>

- Part 1: Install and enable IIS in Windows with CGI:

<sub>***Internet Information Services(IIS) is a web server that allows you to host websites and web applications on a Windows-based server. With IIS, you can create and manage websites, handle incoming web request, and serve web pages to users over the internet. It provides a platform for hosting and running various types of websites.***</sub>
 
1.) Click the Start Menu and type in Control Panel under the search bar.
  
2.) Once in the Control Panel, select 'Programs' > 'Turn Windows Features On & Off'.
  
3.) Enable [X] 'IIS' > Expand [+] 'World Wide Web Services' > [+] 'Application Developer' > [X] CGI

  <sub>***CGI allows us to install the PHP manager. The PHP manager will then allow us to install osTicket. 
Common Gateway Interface(CGI) needs to be enabled on IIS in order to install osTicket because osTicket relies on CGI scripts to process and handle certain web requests.***</sub>

4.) Once IIS has been enabled and installed, we can check that everything is working by typing '127.0.0.1' into the search bar of our web browser.
  
<sub>***'127.0.0.1' is the loopback address for our local machine. The loopback address refers to the computer itself, which will allow you to access the web server or any other services running on your own machine***</sub>
  
- Part 2: Install PHP Manager for IIS:
  https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view
  
- Part 3: Download and Install Rewrite Module:
  https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view?usp=share_link
  
- Part 4: Create a Directory for PHP on the local C:drive.

1.) Open 'File Explorer' > 'My PC' > C:drive > 'New' > 'Folder' > name the folder 'PHP'
  
- Part 5: Download PHP 7.3.8 and Unzip Contents into C:PHP
  https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=share_link
  
1.) Use the link provided and download the PHP 7.3.8(Leave all files as they are, we will extract them onto the PHP folder after.
 
2.) Locate the file and extract it to 'C:PHP folder'.
 
- Part 6: Download and Install C++ Restributable:
 https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view?usp=share_link
 
- Part 7: Downoad and Install MySQL Server:
 https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view?usp=share_link
 
 1.) Follow THIS installation process for MySQL:
 -Typical Install
 -Standard Configuration
 -Username: 'root' pw: 'Password1'
 -Exectute and Finish
 
- Part 8: Confgiue ISS as Admin and Register PHP
1.) Type 'IIS' in the search bar on Windows Desktop > Right click to 'Run as Administrator'
2.) Double click PHP manager > 'Register New PHP version'
3.) Click the three dots icon to browse > 'PHP' folder > 'PHP-CGI' > select 'OK'
4.) Click 'Restart' so the system can reset with PHP now added.
 
- Part 9: Download and Install osTicket:
 https://drive.google.com/file/d/1VeVXKlzHDRjeaVUL99ptq7qYbrbXdFxJ/view?usp=share_link
 
- Part 10: Downloading osTicket and Setting up IIS:
 1.) Once osTicket has been downloaded, open 2 windows of 'File Explorer'. We will be extracting and copying the 'upload' Folder to 'c:\inetpub\wwwwroot:'
-File Explorer 1: Navigate to 'Downloads' > osTicket > Unzip contents > this is where you will see the 'upload' folder.
-File Explorer 2: My PC > C:drive > inetpub > wwwroot
-Drag and drop 'upload' folder in 'wwwroot'
-Rename the 'upload' folder to 'osTicket'
-Go back to IIS to load the osTicket website
-Once IIS has been opened, navigate to 'VM-osTicket' > Expand [+] Sites > Expand[+] Default Web Site > Select 'osTicket' > Select 'browse *.80' which will then opne the osTicket installer website.
 
- Part 11: Enabling IIS extensions:
 1.) Navigate back to 'IIS' > select 'VM-osTicket' > [+] 'sites' > [+] 'Default Web Site' > 'osTicket' > 'PHP Mangager'
 2.) Select 'Enable or disable an extension'
 3) Enable the following extensions:
 php_impa.dll
 php.intl.dll
 php.opcache.dll
 4.) Go back to the osTicket in the browser > Refresh > you'll notice that some red X's has now turned green.
 
 - Part 12: Rename ost-config.php & Changing Access Permissions:
 
 <sub>***Our goal is to change 'C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php' into 'C:\inetpub\wwwroot\osTicket\include\ost-config.php'
  
1.) Navigate to 'File Explorer' > 'This PC' > C:Drive > 'inetpub'> 'wwwroot' >osTicket > 'include' folder.
2.) Scroll down within the 'include' folder until you find 'ost-sampleconfig
3.) Rename to 'ost-config'.
4.) Right click 'ost-config' file > 'properties' > 'Security' > 'Advanced'
5.) Select 'Disable inheritance' > 'remove all permissions'
6.) Add permissions: selct 'add' > 'select a principal' > type 'Everyone' & 'check names' > 'Full Control' > 'Apply' and 'OK'
  
- Part 13: Continue Setting up osTicket in the Browser:
 
1.) In the browser, select 'continue'
2.) Fill in the fields
3.) Install HeidiSQL: https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit

Follow these steps when installing HeidiSQL:

-Open the installation file for HeidiSQL

-Select 'Next' on everything > 'Install' > 'Finish'
 
-Another window of 'Launch Heidi' Will open > click 'New' because we are going to create a new connection to the Database
  
-The username:'root', pw: 'Password1' > select 'Open'
  
-Now we have our connection to MySQL server > create a new database called 'osTicket'
  
4.) We can now finish setting up osTicket in the browser:
 
-Username: 'root', pw: 'Password1'

-Database name: 'osTicket'
  
-'Install now'

- Part 14: Clean up
  
1.) Delete the 'Set Up' folder in 'C:inetpub\wwwroot\osTicket\setup
  
2.) Set permissions to 'Read Only' within C:\inetpub\wwwroot\osticket\include\ost-config.php
  
- Part 15: Testing the Log in:

-Admin Login: http://localhost/osTicket/scp/login.php
  
-End-User Login(where individuals can create tickets): http://localhost/osTicket/
  
  
  
 
 
