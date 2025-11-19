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

<h2>List of Prerequisites </h2>

  - Azure Virtual Machine
  - osTicket Installation files
  - Heidi SQL

Installation Steps

<img width="1643" height="710" alt="OS 1" src="https://github.com/user-attachments/assets/9868d6bf-439e-421d-a935-73e015056f37" />

Create a resource group in Microsoft Azure named osTicket. Then create a virtual machine within this resource group. Use a Windows 10 Pro image for the VM, ensuring it has at least 2 vCPUs. The VM will serve as a space for practice.

<img width="406" height="254" alt="OS 2" src="https://github.com/user-attachments/assets/d8562418-10e9-406f-afd8-879c5ccfca43" />


Next, access the VM via Remote Desktop Protocol (RDP). Copy the Public IPv4 address listed in the Azure portal for the VM and use it to establish the RDP connection.


<img width="418" height="377" alt="OS 3" src="https://github.com/user-attachments/assets/4c0b8202-1dc9-45ed-b404-6f3f59796508" />

Once connected to the VM, enable IIS by opening the Control Panel and navigating to Turn Windows Features On or Off. Scroll down to locate Internet Information Services (IIS) and select the checkbox to activate it.

![OS 4](https://github.com/user-attachments/assets/35efba6c-d51f-4c3b-a61f-025d4453e43b)

https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD Next, use the provided download link to obtain all the necessary files to install and launch osTicket. From the osTicket Installation folder, locate and install PHP Manager to proceed with the setup.

![OS 5](https://github.com/user-attachments/assets/07e94eb1-e1e4-45da-a45f-e8343d6a0a1b)

Within the same folder, install the Rewrite Module to continue configuring the environment.

![OS 6](https://github.com/user-attachments/assets/27fe04e7-78d9-4107-8d1a-514b44c39f91)

Create the directory C:\PHP. Unzip the file PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and extract all its contents into the C:\PHP directory.

![OS 7](https://github.com/user-attachments/assets/9c36ac25-d33b-43f3-8ee5-0e56e37b6a28)

Install VC_redist.x86.exe from the osTicket Installation folder to ensure the necessary Visual C++ Redistributable components are in place.

![OS 8](https://github.com/user-attachments/assets/0f9f02ef-5f8a-4c72-bb6c-0de4a3b14911)

Install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the osTicket Installation folder to set up the MySQL database server.

<img width="497" height="389" alt="OS 9" src="https://github.com/user-attachments/assets/12a03809-0c79-4e9c-99e3-6c6f3f9bad1b" />

Open IIS Manager as an administrator. Register PHP within IIS by configuring the necessary settings. Afterward, restart the server by selecting Restart in the IIS Manager.

<img width="1421" height="749" alt="OS 10" src="https://github.com/user-attachments/assets/58ca00cf-03a5-4bbe-8515-59c08687b600" />


From the osTicket-Installation-Files folder, unzip osTicket-v1.15.8.zip and copy the upload folder to C:\inetpub\wwwroot. Then, within C:\inetpub\wwwroot, rename the upload folder to osTicket.

<img width="1422" height="990" alt="OS 11" src="https://github.com/user-attachments/assets/ff306395-09c6-4423-907d-3d56c6a526d3" />

Return to IIS Manager and restart the server. Enable the necessary PHP extensions by navigating to Sites -> Default -> osTicket, then double-click PHP Manager. Select "Disable or enable an extension" and enable php_intl.dll, php_opcache.dll, and php_imap.dll. Afterward, refresh the osTicket web server and verify that the Intl Extension is now enabled.


<img width="1427" height="749" alt="OS 12" src="https://github.com/user-attachments/assets/60237f42-38e3-4710-ade7-f934778823cf" />

Navigate to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename the file to ost-config.php in the same directory (C:\inetpub\wwwroot\osTicket\include).

<img width="1126" height="802" alt="OS 13" src="https://github.com/user-attachments/assets/d799fd46-f04d-48de-a391-4c96b466a01f" />


Assign the appropriate permissions to ost-config.php by right-clicking the file and selecting Properties. In the Security tab, disable inheritance, remove all existing permissions, and grant Everyone full access.

<img width="925" height="589" alt="OS 14" src="https://github.com/user-attachments/assets/73ec896e-66f4-449b-af76-10af4c2bb451" />

Finally, proceed with the osTicket setup in your browser by clicking Continue. Assign a name to your helpdesk as desired, and select a default email address to receive customer-submitted ticket notifications. Congrats!
