# Creating-Domain-Users

### Objective
To practice real-world user management within an Active Directory Domain Services (AD DS) environment. This includes adding users, managing permissions, and organizing accounts using best practices. The project focuses on the following goals:
- Add and configure domain users in a secure and structured way.
- Organize default and custom security groups for clarity and manageability.
- Follow best practices for admin account usage and user permission levels.
- Prepare the Active Directory environment for applying Group Policy Objects (GPOs).
- Practice Organizational Unit (OU) Structuring:
- Create a logical and scalable hierarchy of OUs to manage users by department, location, or role.
- Simulate a real enterprise structure with nested OUs.

### Skills Learned
- User provisioning in Active Directory
- OU and security group organization
- Windows Server 2022 administration
- Secure account management practices<br>
  <br>
### Tools Used
- Windows Server 2022 (AD DS Role Installed)
- Server Manager
- Active Directory Users and Computers (ADUC)
- Proxmox Virtual Environment<br>

<hr style="border: 0.15px solid rgba(0, 0, 0, 0.05);">
  
### Step 1: Navigate to ADUC via Server Manager
- Open Server Manager.
- Go to Tools > Active Directory Users and Computers.<br>

<img src="https://github.com/user-attachments/assets/00d8de4a-2215-44d3-84f4-2c9ba5c718c2" width="1000"><br>
<br>

<hr style="border: 0.15px solid rgba(0, 0, 0, 0.05);">

You will see domain (e.g., DOOM.local) listed in the left-hand pane.<br>
<br>
- Under the Computers folder, any domain-joined computers would be visible.
- The Domain Controllers folder shows all domain controllers (in this case, only DC01).<br>
<br>
This structure helps you visually manage and locate all domain-connected devices and services. Understanding where users and domain roles reside is critical for maintenance and troubleshooting.<br>  
<br>
<img src="https://github.com/user-attachments/assets/b3584863-f491-4280-9a92-45ae4d55ec0d" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 2: Create an Organizational Unit (OU)
- Right-click your domain name (e.g., DOOM.local) > New > Organizational Unit.
- Name it something like Groups.<br>
<br>
Using OUs allows you to organize users separately from default built-in accounts. This supports better security, scalability, and simplifies applying group policies.<br>
<br>

<img src="https://github.com/user-attachments/assets/12f7e975-ab8c-4d86-b42e-afde373f9cbf" width="1000"><br>
<br>
<img src="https://github.com/user-attachments/assets/29394860-c1df-48af-8fea-11937933fe81" width="1000"><br>
<br>
<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 3: Move Default Security Groups to the OU
Drag and drop built-in security groups from the Users folder to the new Groups OU. Keeps the Users folder clean and focused on actual user accounts. Helps avoid confusion and maintains proper structure within Active Directory.<br>
  <br>

<img src="https://github.com/user-attachments/assets/c30753d6-2063-4985-8f98-e252d00f17ba" width="1000"><br>
<br>
<img src="https://github.com/user-attachments/assets/51211156-bc55-4531-8bf9-85796f4e171d" width="1000"><br>

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 5: Resolve PCI Simple Communications Controller Driver
Installed missing drivers by:<br>
<br>
1. Opening Device Manager  
2. Right-clicking PCI Simple Communications Controller  
3. Selecting “Browse my computer for drivers”  
4. Navigating to VirtIO ISO and selecting the correct subfolder (e.g., NetKVM, Balloon)  
5. Letting Windows search and install the driver

<img src="https://github.com/user-attachments/assets/47aa077a-3c16-4f99-9596-a20de87ecf43" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 6: Fixing Keyboard Input Issues
Resolved keyboard input errors and random shortcut triggers by:<br>
<br>
- Opening Advanced Keyboard Settings  
- Changing the input method to English (United States) – US

<img src="https://github.com/user-attachments/assets/66a9f586-c9d7-4ebe-9e71-f7051a4f2120" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 7: Complete Setup and Assign Static IP
Finalized the administrator account setup and configured a static IP address manually.
Updated the IP address, subnet mask, gateway, and DNS settings to place the server on a secure internal network.<br>
<br>

<img src="https://github.com/user-attachments/assets/5ac9ae4a-a162-4b46-916e-921a02398c52" width="1000">
<img src="https://github.com/user-attachments/assets/40c7428d-d2ed-4b95-890a-c0ccd8be208f" width="1000">
<img src="https://github.com/user-attachments/assets/898e6c2b-8cd1-4d2d-855f-441314f267d6" width="1000">
<img src="https://github.com/user-attachments/assets/f87a7e7c-52f5-4cce-b74e-cb404372d9a0" width="1000">


