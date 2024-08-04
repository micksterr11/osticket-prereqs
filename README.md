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

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Link for [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
- Install/Enable Internet Information Services (IIS) in Windows with CGI and Common HTTP Features
- Install PHP Manager for IIS
- Install Rewrite Module
- Create the directory C:\PHP
- Install PHP and extract contents into C:\PHP
- Install Microsoft Visual C++
- Install MySQL
- Install osTicket
- Install HeidiSQL

<h2>Installation Steps</h2>

<p>
<img src="https://github.com/user-attachments/assets/bf3b1067-fb6f-491d-ae75-2c9677bf1aa1"/>
</p>
<p>
Install/Enable IIS by going to Control Panel>Programs>Turn Windows features on or off>Internet Information Services. Expand Internet Information Systems and Application Development Features and check CGI, then collapse and expand Command HTTP Features and check all boxes. Click OK.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/7d8acbc6-37cb-4fdc-88eb-21c80b92edca"/>
</p>
<p>
Download and install PHP Manager for IIS.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/2b6d1526-bec7-4ffc-8a56-c5f4ac6ecd55"/>
</p>
<p>
Download and install Rewrite Module. 
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/cb204b79-c13a-423f-818a-65b8982a1fba"/>
</p>
<p>
First create the directory C:\PHP by going to This PC>Windows(C:) and creating a new folder named 'PHP'. Next, download PHP and extract the contents into C:\PHP. 
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/654feaab-238b-487f-98e2-23660782a10f"/>
</p>
<p>
Download and install Microsoft Visual C++ Redistributable. 
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/82c0d6f1-e888-4739-a88e-a71c7f734143"/>
</p>
<p>
Download and install My SQL Server. Click Typical Setup and launch configuration wizard after install. Choose Standard Configuration and create a root password. Click 'Execute' and 'Finish'.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/e18edf8d-5b7e-4367-a03f-d51d23080077"/> <img src="https://github.com/user-attachments/assets/97f55379-471e-4c4d-8909-7b972b093535" :height=70% width=70%"/> <img src="https://github.com/user-attachments/assets/2b9cef2d-c835-4f10-beca-61226939894a" :height=50% width=50%"/>
</p>
<p>
Run IIS as an Admin. Register PHP from within IIS. To register, provide the path "C:\PHP\php-cgi.exe" Restart IIS.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/c832317b-acca-4fa5-bfbf-ac1831d2cf6f"/>
</p>

<p>
Download osTicket. Extract and copy "upload" folder to C:\inetpub\wwwroot. Within C:\inetpub\wwwroot, rename "upload" to "osTicket". Restart IIS.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/335c00e5-9e85-4b24-b263-eee223339b1f" :height=70% width=70%"/>
</p>

<p>
In IIS, sites>Default Web Site>osTicket>PHP Manager>Enable or disable extension. Enable "php_imap.dll", "php_intl.dll", "php_opcache.dll". Go to sites>Default>osTicket and, on the right, click "Browse *.80".
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/46e52080-b642-45ef-8804-3b3b75f64fa9"/> <img src="https://github.com/user-attachments/assets/acaccf88-d062-4b07-8632-d3bf13c1fc7b" :height=80% width=80%"/> <img src="https://github.com/user-attachments/assets/e4596c77-7c74-4edb-8c17-dd54d7da79c7"/>
</p>

<p>
Rename the file "ost-sampleconfig.php" to "ost-config.php" File path: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
</p>
<p>
Right click the file "ost-config.php" Properties>Security>Advanced>Disable Inheritance>Remove all. Next you will add permissions by clicking Add>Select a Principal, type "Everyone" into the object names, click "Check Names", and click OK. Finally, select "Full Control" and Apply.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/06aa3a79-4ee9-47c0-821b-08d909a5e4bc"/>
</p>

<p>
Continue setting up osTicket in the browser by clicking Continue. Provide a name for the HelpDesk and a default email. Fill out the fields for Admin User.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/648e481f-e816-405e-8526-bab74da04a34"/> <img src="https://github.com/user-attachments/assets/1f778fd3-95cb-4a83-9c2c-a1158e1e05d4" :height=50% width=50%"/> 
</p>
<p>
<img src="https://github.com/user-attachments/assets/86337630-4ce9-4c26-83de-7800112f921b"/>
</p>
<p>
Install HeidiSQL and launch once finished. Click "New", provide the root password that was previously created, and Open. Right click "Unnamed", select Create New>Database, and create a database named "osTicket".
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/d8589c79-a4cb-4974-b855-9f5ef53d3461"/>
</p>

<p>
Back to the browser under Database Settings, type "osTicket" in the MySQL Database field. For MySQL username and password, the username will be 'root' and the root password previously created. Click "Install Now".
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/1e879cac-2786-4681-8799-6fa151a77042"/> <img src="https://github.com/user-attachments/assets/c131b9ac-6b59-4363-b609-053dd2b68d64" :height=80% width=80%"/>
</p>

<p>
Your'e done! To clean up, delete C:\inetpub\wwwroot\osTicket\setup and set permissions to "Read" only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
<br />

<p>
Link for Admin Login: http://localhost/osTicket/scp/login.php
</p>
<p>
Link for End Users: http://localhost/osTicket/
</p>
