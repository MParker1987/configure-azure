<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Prepare Your On-Premises Active Directory
- Create a Virtual Network in Azure
- Create an Azure Virtual Machine for AD
- Install Active Directory Services on Azure VM
- Promote Azure VM to Domain Controller
- Configure DNS and Replication
- Secure Communication
- Migrate Users and Resources
- Test and Monitor
- Backup and Disaster Recovery

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://activedirectorypro.com/wp-content/uploads/2022/06/azure-domain-controller-featured.webp"/>
</p>
<p>
<h2>Step 1: Prepare Your On-Premises Active Directory:</h2>

- Ensure that your on-premises AD is properly configured with the correct domain name and functional level. You should have at least one on-premises domain controller set up.
- Verify network connectivity between your on-premises network and Azure. You might need to set up a site-to-site VPN or an Azure ExpressRoute connection for secure communication between the two environments.

<h2>Step 2: Create a Virtual Network in Azure:</h2>
<p>
<img src="https://i.stack.imgur.com/5NW5c.png"/>
</p>
When creating a virtual network in Azure, specify the following details:
- Name: Give your virtual network a descriptive name.
- Address Space: Define the IP address range for the virtual network.
- Subnets: Create one or more subnets within the virtual network for different purposes (e.g., Azure AD, application servers).
- Security Groups: Configure Network Security Groups (NSGs) to control inbound and outbound traffic to and from Azure VMs.
- Ensure that you have a VPN gateway or ExpressRoute circuit set up to establish connectivity between your on-premises network and Azure.

<h2>Step 3: Create an Azure Virtual Machine for AD:</h2>

When creating the Azure VM, specify:
- Operating System: Choose a Windows Server OS version compatible with your on-premises AD.
- Size: Select an appropriate VM size based on your requirements.
- Authentication: Configure authentication settings (usually RDP for Windows VMs).
- Networking: Attach the VM to the virtual network created in Step 2.
- Public IP Address: Assign a public IP address if you need remote access to the VM.
  
<h2>Step 4: Install Active Directory Services on Azure VM:</h2>
<img src="https://activedirectorypro.com/wp-content/uploads/2022/06/create-vm-install-adds-1.webp"/>
After connecting to the Azure VM using RDP:
- Open "Server Manager."
- Navigate to "Manage" > "Add roles and features."
- Select "Active Directory Domain Services" and include the management tools.
- Proceed with the installation and reboot the VM if required.
  
<h2>Step 5: Promote Azure VM to Domain Controller:</h2>
<img src="https://activedirectorypro.com/wp-content/uploads/2022/06/create-vm-install-adds-4.webp"/>
After the installation:
- Open "Server Manager."
- Click "Add roles and features" > "Active Directory Domain Services" > "Promote this server to a domain controller."
- Choose "Add a new forest" and specify the fully qualified domain name (FQDN) for your Azure AD forest.
- Configure the Directory Services Restore Mode (DSRM) password for disaster recovery.
  
<h2>Step 6: Configure DNS and Replication:</h2>

- Ensure that the Azure AD DC uses itself as the primary DNS server.
- Set up DNS settings to allow communication between your on-premises DNS servers and the Azure AD DC.
- Verify that replication between your on-premises DC and the Azure VM DC is working correctly by checking event logs and using tools like "Active Directory Sites and Services."
  
<h2>Step 7: Secure Communication:</h2>

- Configure Azure Network Security Groups (NSGs) to control incoming and outgoing traffic between Azure VMs and your on-premises network.
- Implement secure communication methods such as a site-to-site VPN or Azure ExpressRoute to establish a secure connection between on-premises and Azure.
  
<h2>Step 8: Migrate Users and Resources:</h2>

If needed, use Azure AD Connect to synchronize on-premises users, groups, and resources with Azure AD. This step ensures that user accounts are accessible in both environments.

<h2>Step 9: Test and Monitor:</h2>

- Test user authentication by joining a test Azure VM to the Azure AD domain and verifying login functionality.
- Monitor the performance and security of your Azure AD using Azure Monitor, which provides insights into Azure resource health, activity logs, and more.

<h2>Step 10: Backup and Disaster Recovery:</h2>

Implement a backup and disaster recovery solution for Azure AD and Azure VMs using Azure Backup and Azure Site Recovery. Regularly back up your Azure AD data and have a disaster recovery plan in place.
</p>
<br />

<p>
<img src="https://activedirectorypro.com/wp-content/uploads/2022/06/create-vm-azure-1.png"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
