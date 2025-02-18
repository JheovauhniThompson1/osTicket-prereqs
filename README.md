<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- HeidiSQL

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Created an Azure Virtual Machine and got Logged in
- Enabled IIS in Windows with CGI
- Installed PHPManagerForIIS_V1.5.0.msi, rewrite_amd64_en-US.msi, VC_redist.x86.exe, and mysql-5.5.62-win32.msi
- Created a "PHP" Folder in the C Drive(C:/), then unzipped php-7.3.8-nts-Win32-VC15-x86.zip into it
- Registered PHP withing IIS 
- Installed osTicket v1.15.8 and Tested it in Browser
- Installed Extensions and configured permisions for Configuration file
- Installed HeidiSQL then finsihed setting up osTicket

<h2>Installation Steps</h2>

<p>
<img src="https://github.com/user-attachments/assets/573109f1-a08e-4884-97d5-4e726408bba5"/>
<img src="https://github.com/user-attachments/assets/9f5b4dc4-c62d-4492-8a5f-74c47992fad5"/>
  
</p>
<p>
The first thing I did was construct a virtual machine in Azure rather than using my actual PC to install osTicket. After that, I launched Remote Desktop and signed into the VM with a username and password I made.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/8348d27c-0db8-48d1-9bb2-108a9663c3f2"/>
<img src="https://github.com/user-attachments/assets/817e7580-06b4-45e0-886c-b15dca5eb52a"/>
</p>
<p>
In this stage, I entered the virtual machine, opened the control panel, navigated to Programs -> Programs and Features -> Turn Windows features on and off, and then selected Internet Information Services. I also expanded Internet Information Services, then expanded Application Development Features, and checked CGI.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/8bcc7486-696f-4107-9adc-82cb4f1bccc9"/>
</p>
<p>
After installing the necessary external software to run osTicket, I registered PHP within IIS and reloaded it to ensure that everything was working properly.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/2452b20e-a24a-461d-a9d2-1e7890543e97"/>
</p>
<p>
I then unzipped the osTicket-v1.15.8.zip file and transferred the "upload" folder to "c:\inetpub\wwwroot". I then renamed the "upload" folder to "osTicket". I also had to restart the IIS server to ensure everything was working properly.
</p>
<br />

<p>
Before Extensions:
</p>
<img src="https://github.com/user-attachments/assets/bf8c2461-1e0b-4ee0-978d-0eeb98028722"/>
</p>
<p>
After Extensions:
</p>
<img src="https://github.com/user-attachments/assets/436e8772-456c-4a20-8a5c-aca8685393f2"/>
</p>
<p>
For this step, I returned to IIS, navigated to Sites -> Default Web Site -> osTicket, and then clicked "Browse *:80". This directed me to Microsoft Explorer, which opened  the osTicket web page. However, I found that I was missing a few extensions. To resolve this, I returned to IIS and navigated to Sites -> Default Web Site -> osTicket, then double-clicking PHP Manager, selecting Enable or disable an extension, and ultimately enabling php_imap.dll, php_intl.dll, and php_opcache.dll. I then refreshed my browser and discovered that I was no longer missing dependencies.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/e7c07aee-3222-4cd7-bd46-099318de6136"/>
</p>
<p>
Next, I renamed the file "ost-sampleconfig.php" to "ost-config.php". To allow os Ticket to configure this file, I needed to grant it permissions on the back end. To accomplish this, I right-clicked ost-config.php, selected Properties -> Security, SYSTEM, and Advanced. After that, I clicked on Disable inheritance to remove all of its present permissions. I then pushed the add button. Then click the "Select Prinicipal" option, set it to Everyone (because I'm not sure what group osTicket belongs to), and check full control.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/7dce28be-138a-4478-97a6-5d15804dcbbf"/>
<img src="https://github.com/user-attachments/assets/d665b37d-7092-4f42-a7ca-3ccbb268a2f6"/>
</p>
<p>
After installing Heidi SQL, I started a new session with the password and login "root" and it connected me to the session. Now, in order for the web browser to use this session, I needed to construct a database called "osTicket", which I did. After that, I proceeded setting up osTicket in the browser and selected "Install Now".
</p>
<br />
