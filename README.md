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

- Created an Azure Virtual Machine and got Logged in
- Enabled IIS in Windows with CGI
- Installed PHPManagerForIIS_V1.5.0.msi, rewrite_amd64_en-US.msi, VC_redist.x86.exe, and mysql-5.5.62-win32.msi
- Created a "PHP" Folder in the C Drive(C:/), then unzipped php-7.3.8-nts-Win32-VC15-x86.zip into it
- Registered PHP withing IIS 
- Installed osTicket v1.15.8
- Item 5

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
I then unzipped the osTicket-v1.15.8.zip file and transferred the "upload" folder to "c:\inetpub\wwwroot". After that, I renamed the "upload" folder to "osTicket".
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After installing the necessary external software to run osTicket, I registered PHP within IIS and reloaded it to ensure that everything was working properly.
</p>
<br />
