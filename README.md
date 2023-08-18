<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>

</p>
<p>



  1. Set up Resources in Azure:
   - Create a Domain Controller VM named "DC-1" using Windows Server 2022.
   - Create a Client VM named "Client-1" using Windows 10, in the same Resource Group and Vnet as the Domain Controller.

2. Ensure Connectivity between the client and Domain Controller:
   - Log in to Client-1 using Remote Desktop and ping DC-1's private IP address.
   - On DC-1, enable ICMPv4 in the local Windows firewall.
   - Check back on Client-1 to see if the ping succeeds.

3. Install Active Directory:
   - Log in to DC-1 and install Active Directory Domain Services.
   - Promote DC-1 as a Domain Controller.
   - Set up a new forest, such as "myadproject.com".

4. Create an Admin and Normal User Account in AD:
   - In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) named "_EMPLOYEES" and another named "_ADMINS".
   - Create a new employee named "Jane Doe" with the username "jane_admin".
   - Add jane_admin to the "Domain Admins" Security Group.

5. Join Client-1 to your domain (myadproject.com):
   - In the Azure Portal, set Client-1's DNS settings to the DC's Private IP address.
   - Restart Client-1 from the Azure Portal.
   - Log in to Client-1 (Remote Desktop) as the original local admin and join it to the domain.

6. Setup Remote Desktop for non-administrative users on Client-1:
   - Log into Client-1 as jane_admin and open system properties.
   - Click "Remote Desktop" and allow "domain users" access to remote desktop.
   - Now, normal, non-administrative users can log into Client-1.

7. Create additional users and attempt to log into Client-1:
   - Log in to DC-1 as jane_admin and open PowerShell_ise as an administrator.
   - Create a new file and paste the contents of this script (link to the script) into it.
   - Run the script to create additional user accounts.
   - Check ADUC to see the new accounts in the appropriate OU and attempt to log into Client-1 with one of the accounts.

Remember to clean up your Azure environment by closing your Remote Desktop connection and deleting the Resource Group(s) created in the beginning.

I hope this revised guide helps you understand network security protocols and observe traffic between virtual machines. Feel free to use a PC or a Mac, with the Mac requiring an extra step to download the Remote Desktop App.Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
