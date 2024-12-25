# 🚫 Under Construction 🚫

<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

## Configuration and Deployment of Active Directory in Azure Cloud VM ##
> This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.
---


## Video Demonstration ##
### [<img src="https://img.icons8.com/?size=100&id=19318&format=png&color=000000" align="center" width="40" height="40">](https://www.youtube.com/channel/UC9YvuJxKB94ByhwCfZQ_5Kg) [Active Directory Configuration and Deployment](https://youtu.be/3yO0TNwbC_k)

## Environments and Technologies Used ##

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

## Operating Systems Used ##

- Windows Server 2022
- Windows 10 

## High-Level Deployment and Configuration Steps ##

- Install Active Directory Domain Services
- Deploying Active Directory
- Create Users with PowerShell
- Group Policy and Managing Accounts
---

## Deployment and Configuration Steps ##

<img alt="ADinstall" src="https://github.com/user-attachments/assets/7600bdf8-df2e-4276-ae3d-6de2dd5d3d68" /> <br />

:one: Install Active Directory Domain Services ⤵️
> Promote as a Domain Controller (DC)
>   - Setup a new forest as **talondomain.com**
>   - Restart and log back into DC as user: **talondomain.com\talons**
---

<img alt="deploy2" src="https://github.com/user-attachments/assets/ec1f8d82-c316-4b01-bd66-254880c3d7ae" /> <br />

:two: Create a Domain Admin user within the Domain ⤵️
> In Active Directory Users and Computers (ADUC):
>  - Create an Organizational Unit (OU) called `_EMPLOYEES`
>  - Create another new OU named `_ADMINS`
>  - Create a new employee named `Jane Doe` with username: `jane_admin` 
>  - Add **Jane Doe** user to the `Domain Admins` Secuirty Group
>  - Logout of DC as **talondomain.com\talons**, Log back into DC as **talondomain.com\jane_admin** <br />

<img src="https://github.com/user-attachments/assets/6f38000f-da1c-4062-92e1-c2d82ae84e91" alt="deploy3"/> <br />

3️⃣ Join **client-1** to your Domain ⤵️ 
> - From Azure Portal:
>   - Set **client-1** DNS settings to DC's private IP address
> - Login to **client-1** as local admin (ctalons) and join it to the domain
> - Login to DC and verify if **client-1** shows in ADUC
> - In ADUC:
>   - Create a new OU named `_CLIENTS` and add **client-1**
---

<img src="https://github.com/user-attachments/assets/3edab6c0-90d4-48ab-af79-cbdf28afd89e" alt="create1"/> <br />

4️⃣ Setup Remote Desktop for non-admin users on **client-1** ⤵️
> Log into **client-1** as **talondomain.com\jane_admin**
> - Open **System Properties**
>   - Click **Remote Desktop**
>   - Allow **domain users** access to remote desktop
> - You can now log into **client-1** as non-admin user

⚠️ This task is usually done with **Group Policy** which allows you to change many systems at once ⚠️ <br />

<img src="https://github.com/user-attachments/assets/5b660615-87f6-4a62-993d-04f9c2ee2182" alt="create2"/> <br />

5️⃣ Creating additional users with Powershell script ⤵️
> Log into **DC-Jane Doe**
> - Open **Powershell_ise** as an administrator
>   - Create a new file and paste contents of script
>   - Run the script and observe the accounts being created
> - Open ADUC and observe the new accounts created under **_EMPLOYEES** OU
> - Log into **client-1** with one of the new user accounts
---

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />

> Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
---
