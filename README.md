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

### Step 4: Understand Built-In Administrator Account
Double-click the built-in Administrator account to view its properties.
- This account was configured during initial domain setup and has full control over the domain.
- Avoid using this account for daily tasks. Create a lower-privileged user for administrative work. This protects against accidental misconfigurations or attacks using high-level credentials.<br>
<br>
<img src="https://github.com/user-attachments/assets/6a3cb2ea-53c6-4b1a-98f2-6487d449f3c3" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 5: Create a New Domain User
Right-click on your target OU (e.g., ITUsers) > New > User<br>
<br>

<img src="https://github.com/user-attachments/assets/7840a524-4c50-4495-b1ba-3c8a6cdf8203" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

Fill in:
First Name Happy
Last Name Gilmore
Username (format: hgilmore)<br>
<br>
<img src="https://github.com/user-attachments/assets/6d485d91-2019-44e7-93c9-ee81e83e75cb" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

Click Next, set a secure password. Choose whether the user must change their password at next logon. Click Finish to complete.<br>
<br>
For security, real environments often use randomly generated temporary passwords and enforce password reset at first login. User properties can be edited further by double-clicking the user account.<br>
<br>
<img src="https://github.com/user-attachments/assets/111b6eda-0734-406f-809d-1ddb79a49217" width="1000"><br>
<br>
<img src="https://github.com/user-attachments/assets/62f2a8a3-7322-417c-a867-21511f99a3a2" width="1000"><br>
<br>
<img src="https://github.com/user-attachments/assets/4c4be718-22d6-4a68-8006-7d57c54e5033" width="1000"><br>

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 6: View or Edit User Properties
Double-click any user to open the Properties window. Add details such as department, job title, contact info, or assign group membership.<br>
<br>
Adding metadata improves directory searchability and helps with filtering users in reports, permissions, and automated scripts.<br>
<br>

<img src="https://github.com/user-attachments/assets/e18e869c-c57b-4376-a8e1-19fe2f2a56b1" width="1000">

<hr style="border: 0.35px solid rgba(0, 0, 0, 0.05);">

### Step 7:  Create More Users Efficiently
Right-click an existing user and choose Copy to quickly clone the structure of a user. Update only the unique fields (e.g., name, username, password).<br>
<br>
Copying saves time and ensures consistency when adding users with similar settings or group memberships.<br>
<br>

<img src="https://github.com/user-attachments/assets/8b561feb-afbf-40c0-b69e-0c560844b0d8" width="1000">

