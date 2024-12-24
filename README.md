# 🚫 Under Construction 🚫

<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

## Active Directory Deployed in (Microsoft Azure) Cloud ##
> This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.
---


## Video Demonstration ##
### [<img src="https://img.icons8.com/?size=100&id=19318&format=png&color=000000" align="center" width="40" height="40">](https://www.youtube.com/channel/UC9YvuJxKB94ByhwCfZQ_5Kg) [Active Directory Configuration](https://youtu.be/3yO0TNwbC_k)

## Environments and Technologies Used ##

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

## Operating Systems Used ##

- Windows Server 2022
- Windows 10 

## High-Level Deployment and Configuration Steps ##

- :one: Install Active Directory Domain Services
- :two: Deploying Active Directory ➡️ 3️⃣
- :four: Create Users with PowerShell ➡️ 5️⃣
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
> - From Azure Portal, set **client-1** DNS settings to DC's private IP address
> - Login to **client-1** as local admin (ctalons) and join it to the domain
> - Login to DC and verify if **client-1** shows in ADUC
> - In ADUC, create a new OU named `_CLIENTS` and add **client-1** to it

---

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

> Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
---
