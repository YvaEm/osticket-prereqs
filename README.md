<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)


<h2>Installation Steps</h2>


<p>
Log into the VM with Remote Desktop</p>

![Screenshot 2024-12-21 192532](https://github.com/user-attachments/assets/d3756935-15e1-498c-9626-9341692166f0)

<br />



<p>
Within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip it onto your desktop.
  
The folder should be called “osTicket-Installation-Files”

We will use the files in this folder to install osTicket and some of the dependencies.

![Screenshot 2024-12-21 193307](https://github.com/user-attachments/assets/2af6e58b-3aa5-4066-b486-3f4535bdf2ff)
![Screenshot 2024-12-21 193326](https://github.com/user-attachments/assets/fd7f6a7c-3c72-4e82-a58a-1115f4a1fd17)

  
</p>
<br />


<p>
Install / Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI
  
![Screenshot 2024-12-21 193607](https://github.com/user-attachments/assets/32ac4e22-96d3-476c-98c9-0d7e0c9be7c1)
![Screenshot 2024-12-21 193623](https://github.com/user-attachments/assets/47afa9e5-c2dc-46ad-a20e-7f6dadcc21d5)
![Screenshot 2024-12-21 193720](https://github.com/user-attachments/assets/19c30bdf-ad71-43fa-96d2-ecd116e862cb)
![Screenshot 2024-12-21 193807](https://github.com/user-attachments/assets/ff6b50ec-0baa-4922-a71f-4ff5fe201ed3)

  
</p>
<br />


<p>
From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

![Screenshot 2024-12-21 193928](https://github.com/user-attachments/assets/7530fcf2-093f-4e02-a67f-724dcb8e8f61)

![Screenshot 2024-12-21 193953](https://github.com/user-attachments/assets/1dc123f7-64ef-4c4f-bab5-96623b833bfd)

 
</p>
<br />


<p>
From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

![Screenshot 2024-12-21 194019](https://github.com/user-attachments/assets/a8beb8bd-39cf-42d2-92de-4905991ed33e)

  
</p>
<br />


<p>
Create the directory C:\PHP</p>

![Screenshot 2024-12-21 194855](https://github.com/user-attachments/assets/95e6232e-35e5-4813-ab88-625edee12f76)


<br />


<p>
From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder</p>

![Screenshot 2024-12-21 195008](https://github.com/user-attachments/assets/e258c7f5-bbc3-46fe-b58d-5d3a8ce8f4ae)


<br />


<p>
From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.</p>

![Screenshot 2024-12-21 195051](https://github.com/user-attachments/assets/ed2fc4f1-b695-4e6b-9a64-63a1b1859e33)


<br />


<p>
From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi
  
```
  Typical Setup ->
  Launch Configuration Wizard (after install) ->
  Standard Configuration ->
  Username: root
  Password: root
```

![Screenshot 2024-12-21 195202](https://github.com/user-attachments/assets/ed8b0daa-7b24-48f1-932b-bde75426d338)

![Screenshot 2024-12-21 195213](https://github.com/user-attachments/assets/25790c4b-38ec-49ac-bcca-d6f90accf6c0)

![Screenshot 2024-12-21 195238](https://github.com/user-attachments/assets/8b800837-c1aa-4244-925b-06db68876fd0)

![Screenshot 2024-12-21 195347](https://github.com/user-attachments/assets/adf82548-31cb-4392-92b8-aed689f592ca)

![Screenshot 2024-12-21 195555](https://github.com/user-attachments/assets/75ece6b5-08df-4254-bc50-3745b468edf0)


</p>
<br />


<p>
Open IIS as an Admin


![Screenshot 2024-12-21 195710](https://github.com/user-attachments/assets/04a5e9cc-4784-44a6-8526-e7410c76825b)


Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

![Screenshot 2024-12-21 201916](https://github.com/user-attachments/assets/80687d36-1de1-46c3-bd9f-3ab87f1032fe)

![Screenshot 2024-12-21 201936](https://github.com/user-attachments/assets/8c5fbed6-7941-4079-ab76-8c24483d3201)

![Screenshot 2024-12-21 201959](https://github.com/user-attachments/assets/6f9c669d-5561-445a-90bf-c1ae853008c1)

![Screenshot 2024-12-21 202040](https://github.com/user-attachments/assets/5ce951c7-883c-4d3d-b5af-0a0a23f7bd47)


Reload IIS (Open IIS, Stop and Start the server)

![Screenshot 2024-12-21 202146](https://github.com/user-attachments/assets/81bcef96-32c9-4f3e-89e9-f69f3ce7e9cc)



</p>
<br />


<p>
Install osTicket v1.15.8c


  From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”


  ![Screenshot 2024-12-21 213517](https://github.com/user-attachments/assets/439dcbe2-3fc9-4bb3-aa9a-09ad825858d3)


  ![Screenshot 2024-12-21 213658](https://github.com/user-attachments/assets/e01a55c4-2800-4972-bc2d-6a1d043c4f1c)



  Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”


   ![Screenshot 2024-12-21 213936](https://github.com/user-attachments/assets/82f73f6b-c12f-4336-9a58-320c7d70b1b0)



Reload IIS (Open IIS, Stop and Start the server)

![Screenshot 2024-12-21 202146](https://github.com/user-attachments/assets/35592d92-22b8-4ecb-9ac1-0a7c0bacb94a)


<br />


<p>
Go to sites -> Default -> osTicket
  
On the right, click “Browse *:80”

![Screenshot 2024-12-21 214738](https://github.com/user-attachments/assets/4df82c61-8b81-4ac4-9e70-74302b3902ad)


</p>
<br />


<p>
Note that some extensions are not enabled


![Screenshot 2024-12-21 214930](https://github.com/user-attachments/assets/75c17cda-28d3-4006-8264-7aae34fdc4e5)

  
Go back to IIS, sites -> Default -> osTicket

Double-click PHP Manager

Click “Enable or disable an extension”


![Screenshot 2024-12-21 215209](https://github.com/user-attachments/assets/ce993e86-794e-4c75-8efd-f86d84e01a4a)


```
  Enable: php_imap.dll
  Enable: php_intl.dll
  Enable: php_opcache.dll

```

![Screenshot 2024-12-21 215303](https://github.com/user-attachments/assets/df72312b-7afb-4e52-a065-e0f2fd94a23e)
  
Refresh the osTicket site in your browser, observe the changes

![Screenshot 2024-12-21 215435](https://github.com/user-attachments/assets/22e01fe0-3cdf-4919-ac7f-ecd4507accb0)


</p>
<br />


<p>
Rename: ost-config.php
  
```
  From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
  To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
```

![Screenshot 2024-12-21 215605](https://github.com/user-attachments/assets/a51f12c0-7635-4d38-b1ab-87b477dc0486)

![Screenshot 2024-12-21 215704](https://github.com/user-attachments/assets/429c56f8-1418-44b7-9b1d-c1c86f3286ff)


</p>
<br />


<p>
Assign Permissions: ost-config.php 

Right click :ost-config.php and click properties 

![Screenshot 2024-12-21 215704](https://github.com/user-attachments/assets/99d95be8-feef-47fe-a128-7f92bfba904b)


```
  In ost-config.php properties click Advanced 
  Disable inheritance -> Remove All
  In Advanced Security Settings for ost-config.php click Add
  New Permissions -> Everyone -> All
```

![Screenshot 2024-12-21 215931](https://github.com/user-attachments/assets/f3002d46-a1ec-47f8-8e59-f5b3b91fdc5e)

![Screenshot 2024-12-21 220019](https://github.com/user-attachments/assets/be9f9f0a-774b-401b-b505-072cad00a9ef)

![Screenshot 2024-12-21 220032](https://github.com/user-attachments/assets/cbecb810-5c95-4ca8-82f6-426ddb6b8815)

![Screenshot 2024-12-21 220046](https://github.com/user-attachments/assets/6e658937-25fe-4289-8a4d-43f8ee037112)


  
</p>
<br />


<p>
Continue Setting up osTicket in the browser (click Continue)

![Screenshot 2024-12-21 215435](https://github.com/user-attachments/assets/d793cc73-c18a-4308-ac16-335d8fb27a78)


  
Name Helpdesk
Default email (receives email from customers)

![Screenshot 2024-12-21 220450](https://github.com/user-attachments/assets/4c818d11-81ef-4583-b09c-0ca62915818e)


</p>
<br />


<p>
From the “osTicket-Installation-Files” folder, install HeidiSQL.
Open Heidi SQL
Create a new session, root/root
Connect to the session
Create a database called “osTicket"


![Screenshot 2024-12-21 220450](https://github.com/user-attachments/assets/d5f390b9-d945-43f8-aa1d-7a94967fdd29)

![Screenshot 2024-12-21 220552](https://github.com/user-attachments/assets/518aec4a-0819-48ee-8f9b-1a7b2ccd9a7b)

![Screenshot 2024-12-21 220633](https://github.com/user-attachments/assets/13700066-159f-4112-81eb-6510f044a145)

![Screenshot 2024-12-21 220641](https://github.com/user-attachments/assets/56d7d9b4-d393-4516-9749-407d1e69135d)

![Screenshot 2024-12-21 220719](https://github.com/user-attachments/assets/71f9b50d-cda0-4c6b-b0f3-42bb3e540e7c)

![Screenshot 2024-12-21 220738](https://github.com/user-attachments/assets/b3441d7d-15b2-460b-87d9-3edc40df6090)

  
</p>
<br />


<p>
Continue Setting up osTicket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: root
Click “Install Now!”

![Screenshot 2024-12-21 220821](https://github.com/user-attachments/assets/b9686629-f0c5-4e65-b1a6-5047e7181d73)

  
</p>
<br />


<p>
Congratulations, hopefully it is installed with no errors!

![Screenshot 2024-12-21 220842](https://github.com/user-attachments/assets/36c802a1-4900-47ec-8a88-dd7ffff6f63f)

Browse to your help desk login page: http://localhost/osTicket/scp/login.p</p>

![Screenshot 2024-12-21 221102](https://github.com/user-attachments/assets/7edff734-f4f3-4523-aaa3-371bd5969129)


<br />


<p>
End Users osTicket URL:
http://localhost/osTicket/ 

![Screenshot 2024-12-21 221134](https://github.com/user-attachments/assets/1c603845-27c7-426c-978c-e7e21e7a9629)

  
</p>
<br />


