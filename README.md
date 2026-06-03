# azure-ad-homelab
Built a cloud-based Active Directory environment in Microsoft Azure using Windows Server 2025 to simulate enterprise identity management. Configured AD DS, DNS, OUs, security groups, and user accounts, and documented the full setup process step by step

## Step 1: Creating the VM in Azure 
Created a Windows Server 2025 Datacenter VM using the Azure 
free trial. Selected Standard_DS1_v2 (1 vCPU, 3.5 GB RAM) 
with Azure Spot pricing to minimize costs.
<img width="836" height="1035" alt="image" src="https://github.com/user-attachments/assets/c222f422-c696-4fb9-b943-7e8317e36d23" />

## Step 2: Promoting to Domain Controller and Configuring DNS
From Server Manager click on add roles and features 
<img width="1133" height="423" alt="image" src="https://github.com/user-attachments/assets/122bba8a-af03-406d-8685-91d40b2eaa77" />
Click next until you get to Server roles and install Active DIrectory features and DNS server
<img width="802" height="756" alt="image" src="https://github.com/user-attachments/assets/10636e53-856e-4219-8d46-7f11f1c6a74e" />

Continue with the installation 
<img width="802" height="756" alt="image" src="https://github.com/user-attachments/assets/87bb4368-7c29-455a-8fb4-c3d1ad62339f" />

Once installed click on the prompt to promote to a domain controller 
<img width="1099" height="530" alt="image" src="https://github.com/user-attachments/assets/b075533e-f891-4e58-8c1c-0e18e61b1377" />
Create your root domain name and DRSM password
<img width="753" height="554" alt="image" src="https://github.com/user-attachments/assets/3a66bd40-803b-4419-a4c1-6f44209d31f9" />
<img width="753" height="554" alt="image" src="https://github.com/user-attachments/assets/64538ae3-e3c1-4514-b552-28f68cf1c8e3" />

Review selections and install

<img width="753" height="554" alt="image" src="https://github.com/user-attachments/assets/f3d2c3c1-7ed3-45b8-85ad-f9c98dccb69a" />


## Step 3: Verifying the Domain Controller
After the server restarted, I confirmed the promotion was successful by checking Server Manager. AD DS and DNS now appeared in the left sidebar. I also opened Active Directory Users and Computers from the Tools menu to verify the domain structure was created with the default containers
<img width="1164" height="669" alt="image" src="https://github.com/user-attachments/assets/99ff5d01-1a92-4f1c-9e4d-771de475c322" />
<img width="749" height="497" alt="image" src="https://github.com/user-attachments/assets/aabdf39c-9c34-4fc2-987b-09e34ff684a9" />

## Step 4: Creating Organizational Units
Created OUs to simulate a real company structure. I organized them by department to mirror how a corporate environment would manage users and apply Group Policy.
HR
IT
Sales
Marketing
Finance
To create an OU: right-clicked the domain in AD Users and Computers, selected New, then Organizational Unit, and named it.

<img width="241" height="482" alt="image" src="https://github.com/user-attachments/assets/ef250d60-b97d-4820-937c-0eeb67366bb1" />

## Step 5: Creating User Accounts
Created user accounts within each OU to simulate employees across different departments. Each account was given a temporary password with the "User must change password at next logon" option enabled, which is standard practice in a corporate environment.
<img width="754" height="504" alt="image" src="https://github.com/user-attachments/assets/aa616b2c-db59-40d6-9b3e-c2839f1cf0ef" />

## Step 6: Creating Security Groups and Assigning Members
Created security groups to manage access and permissions. A user can only belong to one OU but can be a member of multiple groups, which is how real organizations control access to resources like shared drives, VPN, printers, and software.
Groups created:
VPN-Access
Remote-Desktop-Users
All-Employees
Department-specific groups (HR-Team, IT-Team, etc.)

<img width="666" height="555" alt="image" src="https://github.com/user-attachments/assets/fcbee2ff-6d3d-487d-b942-605123dfb9c0" />

## Step 7: Simulating a Password Reset
Simulated a common helpdesk task by resetting a user's password through Active Directory Users and Computers. Right-clicked the user, selected Reset Password, and set a new temporary password with the requirement to change it at next logon.
This is one of the most frequent tasks in any IT support role and understanding how to do it in AD is essential.

<img width="754" height="531" alt="image" src="https://github.com/user-attachments/assets/a8586c3f-9fc1-419a-9e20-a6d04dcae694" />



