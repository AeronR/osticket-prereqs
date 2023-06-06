<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

In this document I will be demonstrating how to create the osTicketing system from scratch with the use of Azure Virtual Machines

### Benefits of knowing the ticketing system:

1.) Organization and prioritization of requests.

2.) Centralized communication between users and the IT team.

3.) Improves tracking and accountability.

4.) Enhanced collaboration within the IT team.

5.) Compliance with Service Level Agreements (SLAs).

6.) Creation of knwoledge base for self-service.

7.) Increase customer satisfaction. 

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 Pro (22H2)

<h2>List of Prerequisites</h2>

- Internet Information Services(IIS)
- MySQL 5.5
- Simple versions of x86 PHP up to 7.3
- osTicket v1.15.8

<h2>Installation Steps</h2>

<p>
 
<sub>***These installation steps do not include how to create a Virtual Machine on Azure***</sub>
</p>

<p>

- Part 1: Install and enable IIS in Windows with CGI:

<sub>***Internet Information Services(IIS) is a web server that allows you to host websites and web applications on a Windows-based server. With IIS, you can create and manage websites, handle incoming web request, and serve web pages to users over the internet. It provides a platform for hosting and running various types of websites.***</sub>
 
 <sub>***CGI allows us to install the PHP manager. The PHP manager will then allow us to install osTicket. 
Common Gateway Interface(CGI) needs to be enabled on IIS in order to install osTicket because osTicket relies on CGI scripts to process and handle certain web requests.***</sub>

How to Install and enable ISS in Windows w/ CGI:

1.) Control Panel > Programs > Turn Windows features on & off
  
2.) World Wide Web Services > Application Development Features > [x] CGI > [x] Common HTTP Features

<p>
 <img src="https://imgur.com/7psi7z3.png"
      </p>

3.) Once IIS has been enabled and installed, we can check that everything is working by typing '127.0.0.1' into the search bar of our web browser.
  
<sub>***'127.0.0.1' is the loopback address for our local machine. The loopback address refers to the computer itself, which will allow you to access the web server or any other services running on your own machine***</sub>
 
 <p>
  <img src="https://imgur.com/IBMV2X1.png"
       </p>
  
- Part 2: Install PHP Manager for IIS:
  https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view

  <sub>***PHP Manager is a software tool for Windows servers running IIS. It provides a user-friendly interface to install, configure, and manage PHP installations. It allows administrators to customize PHP settings, manage extensions, handle errors, and optimize server resouces***</sub>
  
- Part 3: Download and Install Rewrite Module:
  https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view?usp=share_link
  
  <sub>***The Rewrite Module is a crucial component of web servers that allows for the manipulation of URLs. For the osTicket, it plays an important role in creating user-friendly and search engine optimized URLs for the system's support ticket pages. This enhances the user experience by providing clear and readable links, making it easier for users to navigate and remember specific ticket URLs***</sub>
  
- Part 4: Create a Directory for PHP on the local C:drive
  
- Part 5: Download PHP 7.3.8 and Unzip Contents into C:PHP
  https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=share_link
   
- Part 6: Download and Install C++ Restributable:
 https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view?usp=share_link
  
  <sub>***Microsoft C++ is required for osTicket because osTicket relies on certain libraries and dependencies that are provided by the Microsoft C++ Redistributable package. By installing it, you ensure that your system has the necessary components to run osTicket smoothly and without any compatability issues***</sub>
 
- Part 7: Downoad and Install MySQL Server:
 https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view?usp=share_link
  
<sub>***MySQL is an open-source relational database management system (RDBMS) that is commonly used to store and manage data for web applications. For the osTicket, MySQL is needed as the underlying database engine for storing and retrieving support ticket data, user information, and other related info. It provides a secure and reliable storage solution for osTicket, allowing efficient management of large volumes of data and ensuring data integrity and consistency***</sub>
  
 **Follow _THIS_ installation process for MySQL:** Typical Install > Standard Configuration > Username: 'root' > pw: 'Password1' > Execute > Finish
  
<p>
  <img src="https://imgur.com/sRJbrfJ.png"
       </p>

 <p>
  <img src="https://imgur.com/bR9u2uL.png"
       </p>
  
  <p>
   <img src="https://imgur.com/90nYw1A.png"
        </p>
                                         
- Part 8: Configure IIS as Admin and Register PHP
   
<sub>***In order to use PHP on a web server, you need to register it. Registering PHP involves configuring the web server software to recognize and process PHP files. This is important because PHP is a server-side scripting language, and registering it ensures that the server can correctly interpret and execute PHP code embedded within web pages. By registering PHP, you enable the server to dynamically generate and serve web content based on PHP scripts, allowing you to build dynamic and interactive websites and applications***</sub>

**Follow _these_ steps:**
Run IIS as Admin > PHP Manager > Register New PHP Version > PHP Folder > PHP-CGI > OK > Restart and reload the IIS
   
<p>
 <img src="https://imgur.com/UDQHyN1.png"
      </p>
 
 <p>
  <img src="https://imgur.com/VJbbxE5.png"
       </p>
  
  <p>
   <img src="https://imgur.com/jPB9YWg.png"
        </p>
 
- Part 9: Download and Install osTicket:
 https://drive.google.com/file/d/1VeVXKlzHDRjeaVUL99ptq7qYbrbXdFxJ/view?usp=share_link
   
<sub>***osTicket is a ticketing system used by businesses to manage customer support requests. It is a centralized platofrm that helps organize, track, and resolve customer issues or tikets efficiently. osTicket is useful because it enables businesses to effectively manage and prioritize customer inquires, ensuring timely resolution and better customer satisfaction. It facilitates communicated between support agents and customers, streamlines ticket management, and ehances overall customer support processes***</sub>
 
- Part 10: Downloading osTicket and Setting up IIS:
  
**Follow _THESE_ steps:** Once osTicket has been downoaded > Open two windows of File Explorer (we are going to extract and copy 'Upload' folder to c:\inetpub\wwwroot:)
   
 **_File Explorer 1_:** Downloads > osTicket > Unzip contents (You will then see the 'Upload' folder)
   
<p>
 <img src="https://imgur.com/4ksVHym.png"
      </p>
   
**_File Explorer 2_:** My PC > C:Drive > Inetpub > wwwroot > Drag and drop 'Upload' foder in wwwroot > rename 'Upload' folder to 'osTicket'
 
 <p>
  <img src="https://imgur.com/MJg23g6.png"
                                         </p>
                                         
**Go back to IIS:** VM-osTicket > [+]sites > [+]Default Web Site > 'osTicket' > Browse .80 (this will then load up the osTicket website, but notice the red x marks, we just need to enable some extensions to get it up and working)
                       
<p>
   <img src="https://imgur.com/KFGWSkq.png"
        </p>
                                                                           
- Part 11: Enabling IIS extensions:

 **Follow _THESE_ steps:** IIS > VM-osTicket > [+] sites >[+] Default Web Site > osTicket > PHP Manager
 
 <p>
  <img src="https://imgur.com/nWqubev.png"
       </p>
 
'Enable or disable an extension' > enable php_imap.dll > enable php_intl.dll > enable php_opcache.dll 
  
  <p>
   <img src="https://imgur.com/TOfSLsL.png"
        </p>
  
Go back to osTicket in browser > Refresh (now some red X's have turned green!)
   
  <p>
   <img src="https://imgur.com/nWpOzKk.png"
        </p>
 
 - Part 12: Rename ost-config.php & Changing Access Permissions:
 
 <sub>***Our goal is to change 'C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php' into 'C:\inetpub\wwwroot\osTicket\include\ost-config.php'***</sub>
  
**Follow _THESE_ Steps::** File Explorer > This PC > C:drive > inetpub > wwwroot > osTicket 'include' folder 
   
 <p>
  <img src="https://imgur.com/ZqCssEO.png"
       </p>
   
rename the 'ost-sampleconfig.php' folder to 'ost-config' > select properties on the 'ost-config' file 
  
  <p>
   <img src="https://imgur.com/z9yduFj.png"
        </p>
  
Security > Advanced
   
   <p>
    <img src="https://imgur.com/ogTvHdq.png"
         </p>

<sub>***osTicket needs to interact with this file in order to run and since we don't know what user it's gong to use, we are going to set the file permissions so that anyone can access it. This will prevent issues when attempting to connect to osTicket***</sub>
    
Disable inheritance > remove all permissions
    
<p>
 <img src="https://imgur.com/WcXqEBo.png"
      </p>
  
Add > Select a principal > Everyone > Check Names > Full Control > Apply > OK
 
 <p>
  <img src="https://imgur.com/qChfAaM.png"
       </p>
  
- Part 13: Continue Setting up osTicket in the Browser:
  
In the osTicket browser select continue > fill out the fields > Install HeidiSQL: https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit

<sub>***HeidiSQL is a ree and open-source database management tool. It provides a GUI for managing and interacting with various database systems. With HeidiSQL, users can perofrm tasks such as executing quieries, managing database structures, importing and exporting data, and performing database administration tasks. It offers a user-friendly interface and supports advanced features like SSH tunneling and SSL encryption, making it a popular choice for developers and database admins***</sub>
  
**Follow _THESE_ steps for installing HeidiSQL:** Next on everything > Install > Finish
  
  <p>
   <img src="https://imgur.com/WrrnjOA.png"
        </p>

  (another window of 'Launch Heidi will open) 
  
  Click new > username: 'root', pw:'Password1' 
   
    <p>
  <img src="https://imgur.com/fx1TTOm.png"
       </p>
   
  Open > Create a new databased called 'osTicket'> Install now
  
     <p>
      <img src="https://imgur.com/TNwYzdy.png"
           </p>
      
     <p>
      <img src="https://imgur.com/1QRf9ul"
           </p>

- Part 15: Testing the Log in:

The final step! To make sure everything is working, simply log in via the websites below.
      
Admin Login: http://localhost/osTicket/scp/login.php
  
End-User Login(where individuals can create tickets): http://localhost/osTicket/
  
  
  
 
 
