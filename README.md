# Active-Directory-and-Powershell

Project: My PowerShell & Active Directory Learning Journey
This repository documents my journey of learning Active Directory and PowerShell by building a virtual lab environment. The goal is to demonstrate my understanding of fundamental concepts and my ability to automate administrative tasks using scripting.

1. The Lab Environment
I used Hyper-V to create a small virtual network for this project. The environment consists of two virtual machines:

Domain Controller (DC01): A Windows Server 2019 VM acting as the primary domain controller for my new domain.

Client Machine (Client01): A Windows 10/11 VM that I joined to the domain. This allows me to test user logins and Group Policy Objects (GPOs) from an end-user perspective.

Software Used:

Hyper-V: The virtualization platform.

Windows Server 2019: The operating system for the domain controller.

Windows 10/11: The operating system for the client machine.

2. Setting Up the Domain Controller
Here are the high-level steps I followed to set up the domain controller:

Virtual Machine Creation: A new virtual machine was created in Hyper-V using a Windows Server 2019 ISO file. I allocated sufficient resources (RAM, vCPUs) to the VM.

Initial Configuration: I configured a static IP address for the server and renamed it to something descriptive like DC01.

Active Directory Domain Services (AD DS) Installation: I used the Server Manager to install the AD DS role.

Promoting to Domain Controller: The server was promoted to a domain controller, creating a new forest and a new domain.

3. Joining the Client to the Domain
After configuring the domain controller, the next step was to join the client machine to the domain. This process involved:

DNS Configuration: I set the client's DNS server to point to the IP address of the domain controller.

Network Configuration: I ensured both the client and the domain controller could communicate with each other on the same virtual network.

Joining the Domain: From the client's System Properties, I changed the machine's domain and provided the credentials for a domain administrator account to complete the process.

This step was critical as it allowed me to test user accounts, group policies, and permissions from a realistic client perspective.

4. Active Directory & PowerShell Scripts
The /scripts directory in this repository contains the PowerShell scripts I created to manage Active Directory objects. Each script is commented to explain its purpose.

Below is a breakdown of what these scripts do:

User Management:

New-ADUserFromCSV.ps1: This script reads user data from a CSV file and creates new user accounts in Active Directory.

Disable-StaleUsers.ps1: This script identifies and disables user accounts that haven't logged in for a specified number of days.

Group Management:

Create-ADGroup.ps1: A basic script to create new security groups.

Add-UsersToGroup.ps1: This script adds a list of users to a specific security group.

Reporting:

Get-UserReport.ps1: Generates a report of all users in a specific Organizational Unit (OU), including their status and last logon time.

5. Key Learnings & Reflections
Throughout this project, I've learned the following:

The importance of planning the AD structure (OUs, groups) before scripting.

How to use the Active Directory PowerShell module to perform administrative tasks that would otherwise be done manually.

The power of automation and how it can save time and reduce human error.

The critical role of DNS in a domain environment.

The process of troubleshooting client-to-domain connectivity issues.

6. What's Next?
My next steps will be to explore more advanced topics, including:

Group Policy Objects (GPOs): Using PowerShell to manage and report on GPOs.

PowerShell Desired State Configuration (DSC): Using code to define and maintain the configuration of my servers.

