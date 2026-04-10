# LBCyberlab
Purpose: Demonstrate practical knowledge in Windows Server and Active Directory for professional portfolio.

Windows Server Domain Controller Lab
Overview
This lab demonstrates how to set up a Windows Server virtual machine in VMware Workstation Pro and promote it to a Domain Controller (DC). It includes networking configuration, Active Directory Domain Services installation, and client domain join steps. Documenting this process provides proof of practical knowledge for resumes and professional portfolios.
________________________________________
Step 1: VMware VM Setup
•	Create a new VM in VMware Workstation Pro.
•	Select Custom (Advanced) setup.
•	Choose I will install the operating system later.
•	Guest OS: Microsoft Windows Server (version matching the VHD).
•	CPU: 2 vCPUs minimum.
•	RAM: 4–8 GB.
•	Networking: NAT (clients can reach internet and DC).
•	Disk: Use existing .vhd file. Switch firmware type to BIOS.
________________________________________
Step 2: Configure Network Settings in Windows Server
•	Open Network and Sharing Center → Change adapter settings → IPv4 Properties.
•	Set:
o	IP Address: 192.168.100.10
o	Subnet Mask: 255.255.255.0
o	Default Gateway: 192.168.100.2 (VMware NAT gateway)
o	Preferred DNS: 192.168.100.10 (self)
o	Alternate DNS: 8.8.8.8 (optional)
•	Rename server to DC01.
________________________________________
Step 3: Install AD DS Role
•	Open Server Manager.
•	Click Manage → Add Roles and Features.
•	Select Role-based installation.
•	Choose server.
•	Check Active Directory Domain Services.
•	Add required features.
•	Click Install.
________________________________________
Step 4: Promote to Domain Controller
•	In Server Manager, click the notification flag.
•	Select Promote this server to a domain controller.
•	Choose Add a new forest.
o	Domain name: lab.local.
•	Set Forest and Domain functional levels to Windows Server 2016 or higher.
•	Leave DNS checked.
•	Enter DSRM password.
•	Click Next → Install.
•	Server reboots automatically.
________________________________________
Step 5: Verify DC Setup
•	Log back in.
•	Open Active Directory Users and Computers → confirm lab.local domain.
•	Open DNS Manager → confirm forward lookup zone.
•	Run nslookup in PowerShell → confirm DC responds as DNS.
________________________________________
Step 6: Join Client Machines
•	On a Windows client VM:
o	Set DNS to DC’s IP (192.168.100.10).
o	Default Gateway: 192.168.100.2.
•	Go to System Properties → Computer Name → Change.
•	Enter domain name (lab.local).
•	Provide domain admin credentials.
•	Reboot client.
________________________________________
Notes
•	Static IP + DNS pointing to DC are critical.
•	NAT networking allows internet access while keeping DC isolated.
•	Snapshots recommended before major changes.
________________________________________
Proof of Practical Knowledge
This documentation can be published on GitHub as a README.md file or shared via LinkedIn/blog to demonstrate:
•	VMware virtualization skills.
•	Windows Server administration.
•	Active Directory setup and client integration.
________________________________________
Next Steps
•	Create Organizational Units (OUs) for Users, Admins, and Servers.
•	Add test accounts and groups.
•	Explore Group Policy Objects (GPOs) for centralized management.
________________________________________
README Draft Suggestions
You can enhance your README.md with the following sections to make it more comprehensive and appealing to recruiters:
Introduction
This lab demonstrates the setup and configuration of a Windows Server Domain Controller using VMware Workstation Pro. It showcases practical skills in virtualization, Windows Server administration, Active Directory Domain Services (AD DS) installation, and client domain integration.
Prerequisites
•	VMware Workstation Pro installed.
•	Windows Server VHD file.
•	Basic understanding of networking concepts.
•	Familiarity with Windows Server and Active Directory.
Detailed Steps
The step-by-step process includes:
1.	Creating a Windows Server VM in VMware Workstation Pro.
2.	Configuring network settings with static IP and DNS.
3.	Installing the Active Directory Domain Services role.
4.	Promoting the server to a Domain Controller and creating a new forest.
5.	Verifying the Domain Controller setup.
6.	Joining client machines to the domain.
Results
By completing this lab, you will have a functional Windows Server Domain Controller managing a domain (lab.local), with client machines successfully joined and able to authenticate.
How to Use This Repo
Clone or download this repository to follow along with the lab steps. Use the documentation to set up your own test environment for learning or demonstration purposes.
Screenshots
You can add screenshots to illustrate key steps or results. Upload images to an /images folder in this repo and reference them in the README using Markdown:
![Description](images/screenshot1.png)
Contact
Connect with me on LinkedIn: [Your LinkedIn Profile URL]
Feel free to reach out for questions or collaboration.
Author: Luis Purpose: Demonstrate practical knowledge in Windows Server and Active Directory for professional portfolio.
You can enhance your README.md with the following sections to make it more comprehensive and appealing to recruiters:
Introduction
Briefly explain the purpose of the lab and what skills it demonstrates.
Prerequisites
List any software, tools, or knowledge needed before starting.
Detailed Steps
Include the step-by-step process (already documented well in this page).
Results
Highlight what was achieved by completing the lab.
How to Use This Repo
Instructions for others who want to replicate or learn from your lab.
Contact
Your professional contact info or LinkedIn profile link.
Would you like me to help you add these sections to your README.md on this page?
Author: Luis
Purpose: Demonstrate practical knowledge in Windows Server and Active Directory for professional portfolio.

