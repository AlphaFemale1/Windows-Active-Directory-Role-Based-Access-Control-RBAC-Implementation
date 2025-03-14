# Windows-Active-Directory-Role-Based-Access-Control-RBAC-Implementation
This project focuses on setting up a Windows Server Active Directory Domain Controller and implementing role-based access control (RBAC) for shared network folders.
🛠️ Technologies Used
	•	Windows Server 2016 (Domain Controller)
	•	Windows 10 pro (Client Machine)
	•	Active Directory Domain Services (AD DS)
	•	Remote Desktop Protocol (RDP)
	•	Group Policy Management (GPO)
	•	NTFS Permissions & Shared Folders

📍 1. Setting Up the Domain Controller (DC-01)
	1.	Renamed the server to DC-01.
	2.	Installed Active Directory Domain Services (AD DS) via Server Manager.
	3.	Promoted the server to a Domain Controller (DC).
	4.	Created a new domain (e.g., yourdomain.local).
	5.	Restarted the server to apply changes.

📍 2. Creating Organizational Units (OUs) & Users
	1.	Open Active Directory Users and Computers (ADUC).
	2.	Created OUs:
	•	Users (for employees)
	•	Groups (for security groups)
	•	Departments (Sales, HR, Finance)
	3.	Created Security Groups:
	•	Sales_Group
	•	HR_Group
	•	Finance_Group
	4.	Created User Accounts and assigned them to their respective groups:
	•	sales_user1, sales_user2 → Sales_Group
	•	hr_user1, hr_user2 → HR_Group
	•	finance_user1, finance_user2 → Finance_Group

📍 3. Enabling Remote Desktop (RDP) for Users
	1.	Open System Properties → Enable Remote Desktop.
	2.	Added users to “Remote Desktop Users” group.
	3.	Configured Windows Firewall rules to allow RDP.
	4.	Restarted Remote Desktop Services (services.msc).
	5.	Tested RDP access from a client machine.

📍 4. Configuring Shared Folders & Permissions

Step 1: Creating the Shared Folder Structure

📂 C:\Shared_Files\
	•	Sales
	•	HR
	•	Finance

Step 2: Assigning NTFS Permissions

Folder	Allowed Group	Permissions
Sales	Sales_Group	Read/Write
HR	HR_Group	Read/Write
Finance	Finance_Group	Read/Write

Step 3: Removing Unnecessary Access
	•	Removed Everyone from permissions.
	•	Ensured only assigned groups can access their respective folders.

Step 4: Testing Access

✅ Logged in as different users to verify folder access restrictions.

📍 5. Security Hardening & Password Policies

✅ Enforced Strong Password Policies

Configured in Group Policy (gpedit.msc):
	•	Minimum password length: 12 characters
	•	Enforce password history: 24 passwords remembered
	•	Password expiration: 60 days
	•	Complexity requirements: Enabled

✅ Restricted Remote Access to Admins Only
	•	Modified Group Policy to allow only Admins & Remote Desktop Users.

✅ Disabled Anonymous Logins
	•	Disabled guest accounts & anonymous enumeration.

📍 6. Final Testing & Verification

✅ Tested Remote Desktop login with different user accounts.
✅ Tested shared folder permissions using different user logins.
✅ Verified security settings (password policy, lockout policy, auditing).

📌 Key Learnings
	•	Active Directory user & group management.
	•	Implementing RBAC (Role-Based Access Control) in Windows.
	•	Hardening security using Group Policy (GPO).
	•	Securing shared folders with NTFS permissions.

📜 Author

👤 Dosunmu Omowunmi
🔗 http://www.linkedin.com/in/dosunmuomowunmielizabeth
 
