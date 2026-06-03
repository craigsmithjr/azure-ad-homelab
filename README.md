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


