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
This structure helps you visually manage and locate all domain-connected devices and services. Understanding where users and domain roles reside is critical for maintenance and troubleshooting.
- Open Server Manager.
- Go to Tools > Active Directory Users and Computers.
- You will see your domain (e.g., DOOM.local) listed in the left-hand pane.
- Under the Computers folder, any domain-joined computers would be visible.
- The Domain Controllers folder shows all domain controllers (in this case, only DC01).<br>
<br>

<img src="https://github.com/user-attachments/assets/f801cb7e-6068-424e-bc1f-73d372cfeb1c" width="1000"><br>
<br>
<img src="https://github.com/user-attachments/assets/d4e14173-c2fd-46db-99d7-92244f0fc116" width="1000">

<hr style="border: 0.15px solid rgba(0, 0, 0, 0.05);">

### Step 2: Configure ISO Boot Order
Updated virtual hardware settings to prioritize the Windows Server ISO as the primary boot device, followed by the VirtIO ISO. This ensures required drivers are available during the OS installation process.<br>
<br>

<img src="https://github.com/user-attachments/assets/96b64655-b705-4a9c-832c-ae5558f0f9fe" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 3: Install Windows Server 2022
Launched the virtual machine and installed Windows Server 2022 (Desktop Experience).
Selected the appropriate region, language, and performed a custom installation. Followed standard setup instructions.<br>
<br>

<img src="https://github.com/user-attachments/assets/22b34de5-f488-4eb5-8a87-a56e0e50e10c" width="1000"><br>
<br>
<img src="https://github.com/user-attachments/assets/fe34e6fe-fb2f-48e4-8777-8eeab7867308" width="1000"><br>
<br>
<img src="https://github.com/user-attachments/assets/d8fe5b20-13e5-40ed-82d9-ac3122889065" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 4: Install VirtIO Drivers
Mounted the VirtIO ISO and installed essential drivers manually to enable disk, network, and input functionality:<br>
<br>
- Red Hat VirtIO Ethernet Adapter  
- VirtIO Balloon Driver  
- VirtIO SCSI Controller<br>
  <br>
Download drivers from:
Download: https://fedorapeople.org/groups/virt/virtio-win/direct-downloads/latest-virtio/

<img src="https://github.com/user-attachments/assets/66d417ad-d099-42f3-bf13-dd85f1464056" width="1000"><br>
<br>
<img src="https://github.com/user-attachments/assets/7ba4528d-32ee-41e6-be4a-d3c67cd01116" width="1000"><br>
<br>
<img src="https://github.com/user-attachments/assets/333c241e-2468-4391-adc9-4bd047cd26d1" width="1000"><br>
<br>
<img src="https://github.com/user-attachments/assets/02163f93-0de1-4754-92ca-e0b8ced2d787" width="1000"><br>
<br>
<img src="https://github.com/user-attachments/assets/05f5b0af-e47c-482d-b420-9707d13ad9ad" width="1000">

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


