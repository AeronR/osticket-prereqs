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
  
  
  
  
  
