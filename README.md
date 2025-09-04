### 🚀 My PowerShell & Active Directory Learning Journey

This repository documents my hands-on journey of learning Active Directory and PowerShell by building a virtual lab from the ground up. The goal is to demonstrate my understanding of core concepts and my ability to automate administrative tasks using scripting.

***

### 1. The Lab Environment: A Virtual Playground

I used **Hyper-V** to create a small but functional virtual network. My environment consists of two key virtual machines:

- **Domain Controller (`WIN10SERVER`):** A Windows Server 2019 VM that serves as the heart of my new domain.
- **Client Machine (`TestPC1`):** A Windows 10 VM that I joined to the domain. This setup allows me to test user logins and Group Policy Objects (GPOs) from a realistic end-user perspective.

**Software Used:**
- **Hyper-V:** My virtualization platform of choice.
- **Windows Server 2019:** The OS for my domain controller.
- **Windows 10:** The OS for my client machine.

***

### 2. Setting Up the Domain

The first phase of the project was all about building the foundation. The process involved:

1.  **VM Creation:** I created both virtual machines from their respective ISO files.
2.  **Initial Configuration:** I configured a static IP for my server and gave it a logical name (`DC01`).
3.  **AD DS Installation:** I installed the Active Directory Domain Services role.
4.  **Domain Promotion:** I promoted the server to a domain controller, creating my very own domain.

***

### 3. Joining a Client to the Domain

This was a critical step in making the lab truly functional. I connected the client machine to the domain by:

1.  **Configuring DNS:** I pointed the client's DNS to the IP of the domain controller.
2.  **Joining the Domain:** From the client's System Properties, I simply entered my new domain and provided administrator credentials to join it.

This step was essential for testing user accounts and permissions, which brought the lab to life.

***

### 4. 💻 My PowerShell Scripts

All the scripts I've created are located in the `/scripts` directory. Each script is well-commented to explain its purpose and functionality.

Here's a quick look at what they do:

- **User Management:**
    - `New-ADUserFromCSV.ps1`: Automates the creation of new users from a CSV file.
    - `Disable-StaleUsers.ps1`: A script to find and disable user accounts that haven't been used for a while.
- **Group Management:**
    - `Create-ADGroup.ps1`: A simple script to create new security groups.
    - `Add-UsersToGroup.ps1`: Adds users from a list to a specific security group.
- **Reporting:**
    - `Get-UserReport.ps1`: Generates a report of all users in a specific Organizational Unit (OU).

***

### 5. 🧠 Key Learnings & Reflections

This project has been an incredible learning experience. Some of my biggest takeaways include:

- **The Power of Automation:** Discovering how PowerShell can save time and reduce manual errors.
- **The Role of DNS:** Understanding why DNS is so critical in an Active Directory environment.
- **Troubleshooting:** Learning to diagnose and fix connectivity issues between the client and the domain controller.

***

### 6. What's Next?

I plan to continue this journey by exploring more advanced topics, such as:

- **Group Policy Objects (GPOs):** Managing and reporting on policies using PowerShell.
- **PowerShell Desired State Configuration (DSC):** Using code to define and maintain my server's configuration.
