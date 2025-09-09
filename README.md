# Installing-Active-Directory-On-Windows-Server

## Windows Active Directory (AD) – Centralized Identity & Access Management
**Windows Active Directory (AD) is a directory service developed by Microsoft that helps manage users, computers, and resources in a network. It is used in enterprise environments to provide centralized authentication, authorization, and security policies.**

## Key Features:
**✅ User & Group Management – Centralized control over user accounts, groups, and permissions.
✅ Authentication & Authorization – Uses Kerberos and LDAP for secure user logins.
✅ Group Policy Management – Enforces security settings, software installations, and network configurations.
✅ Single Sign-On (SSO) – Users can access multiple applications with one set of credentials.
✅ Domain Services – Organizes network resources into domains, forests, and organizational units (OUs).**
## Why Use Active Directory?
**🔹 Centralized Security – Manages access control across the organization.
🔹 Scalability – Supports thousands of users, devices, and applications.
🔹 Integration – Works with Microsoft services like Azure AD, Exchange, and SharePoint.
🔹 Improved Productivity – Users sign in once and access multiple resources without re-entering credentials.**
## Common Use Cases:
**Enterprise IT Management – Controlling access to corporate networks and devices.
User Authentication & SSO – Secure logins for employees across applications.
Access Control & Security – Implementing policies for passwords, firewalls, and permissions.**
Windows Active Directory is essential for managing and securing enterprise networks, ensuring efficient user and resource management. 🚀

## Summary: Setting Up Active Directory on Windows Server 2019
In this project, I installed and configured Active Directory (AD) on Windows Server 2019 to manage users, groups, and computers within an organization. The steps include:

**Installing Active Directory Domain Services (AD DS) on Windows Server 2019.
Creating an Organizational Unit (OU) to structure and manage directory objects.
Adding Users, Groups, and Computer OUs for efficient identity and access management.
This setup enables centralized authentication, authorization, and resource management, ensuring secure and efficient user administration within the domain. 🚀**

## Step - 1
i. Click on **"Manage,"** then select **"Add Roles and Features."**
<img width="1033" height="773" alt="1" src="https://github.com/user-attachments/assets/ee749ab1-5334-40aa-b01d-cf962c36d181" />

## (2) Go to "Server Roles," then select and install "Active Directory Domain Services (AD DS)."
<img width="1024" height="557" alt="2" src="https://github.com/user-attachments/assets/3bfa56cb-3580-4334-acc8-d04cfe669b56" />

<img width="783" height="588" alt="3" src="https://github.com/user-attachments/assets/8ea9fffe-4cec-4532-9543-547c3e685129" />

**iii. Go to the "Confirmation" section and click "Install."**
<img width="1018" height="704" alt="4" src="https://github.com/user-attachments/assets/ef20e3e4-f50b-4dc1-a8c0-2a073f81f7f3" />

**iv. Once the installation is complete, click on "Promote this server to a domain controller."**
<img width="796" height="570" alt="5" src="https://github.com/user-attachments/assets/33a94ee3-7bbf-45eb-befe-2a73980b4303" />

## Why Click on "Promote This Server to a Domain Controller" in Active Directory Setup?
**After installing Active Directory Domain Services (AD DS) on Windows Server 2019, the server needs to function as a Domain Controller (DC). Clicking "Promote This Server to a Domain Controller" is necessary because:**

**✅ Activates Directory Services – It enables the Active Directory database, allowing user authentication, group management, and security policies.
✅ Creates or Joins a Domain – It lets you either create a new domain (e.g., mycompany.local) or add the server to an existing domain.
✅ Manages Authentication & Security – The Domain Controller is responsible for verifying user logins, managing group policies, and securing access.
✅ Enables Group Policies (GPOs) – Once promoted, you can enforce security settings, software deployment, and administrative controls across the network.**

Without promoting the server to a Domain Controller, the installed Active Directory services won't be functional, and the server will not manage users, groups, or policies effectively. 🚀

**v. Click on "Add a New Forest" and enter the root domain name with the .local extension.**
<img width="765" height="561" alt="6" src="https://github.com/user-attachments/assets/5fb0b3dc-6a65-41c5-856e-1bf905417d22" />

**Why Click on "Add a New Forest" in Active Directory Setup? When promoting a server to a Domain Controller (DC), you need to define its role in the Active Directory structure. Clicking "Add a New Forest" is required when setting up Active Directory for the first time**

**Why Use .local for an Active Directory Domain? When setting up Active Directory (AD), you need to choose a domain name for your organization. Many administrators use .local (e.g., company.local) instead of a public domain name. Here’s why:**

**✅ Avoids Conflicts with Public Domains – Using a real domain (e.g., company.com) could cause DNS conflicts if your internal and external resources share the same name. ✅ Simplifies Internal Network Management – .local is only used within the internal network, making it easier to manage internal DNS without affecting public websites. ✅ Prevents Accidental Exposure – A .local domain cannot be resolved on the internet, adding an extra layer of security by preventing external access. ✅ Does Not Require Public DNS Registration – Unlike a real domain (company.com), .local does not need to be registered, saving costs and simplifying setup**

**vi. In the Domain Controller configuration, set and confirm the password for the domain.**
<img width="753" height="559" alt="7" src="https://github.com/user-attachments/assets/551c0a13-aba9-4e2e-a806-7602440f5483" />

**vii. Click "Next" until you reach the prerequisites check, then click "Install."**
<img width="763" height="561" alt="8" src="https://github.com/user-attachments/assets/df7ae3ae-c902-4359-93ed-f431786ec70a" />

**The VM will restart, and once it boots up, you will see that your domain has been successfully created.**
<img width="1072" height="811" alt="9" src="https://github.com/user-attachments/assets/c066b376-7dc6-4804-903b-52b947ae091f" />

**After logging in, you can view the installed components and configured settings within the Active Directory environment.**
<img width="349" height="603" alt="10" src="https://github.com/user-attachments/assets/470c5b81-0e29-4110-9b06-a421c89581dd" />

## Step - 2
**i. Open "Active Directory Users and Computers" (ADUC).**
<img width="1573" height="843" alt="11" src="https://github.com/user-attachments/assets/054230bc-2948-4f02-b18d-d789c0050801" />

**ii. Right-click on your domain and select "New" > "Organizational Unit" to create a new OU.**

**What is an Organizational Unit (OU) in Active Directory? An Organizational Unit (OU) in Active Directory (AD) is a logical container used to organize and manage users, groups, computers, and other objects within a domain. It helps in structuring the directory to apply group policies and delegate administrative tasks efficiently**

**Example of OU Structure: 📂 Company.local (Root Domain) ├── HR (OU) → Users & Computers for HR ├── IT (OU) → Users & Computers for IT Team ├── Finance (OU) → Users & Computers for Finance**

**By using Organizational Units, businesses can structure their Active Directory efficiently, making it easier to manage users, devices, and policies. 🚀**

**ii. I have created an Organizational Unit (OU) named Company, which contains multiple sub-OUs for Users, Groups, Computers, and Servers.**
<img width="1132" height="523" alt="13" src="https://github.com/user-attachments/assets/c4433e15-aacd-4ef7-8bc4-32e4fe054918" />

**iii. Steps to Create a New User**
<img width="925" height="482" alt="14" src="https://github.com/user-attachments/assets/e51e70e9-916a-4107-90a7-faaae4545634" />
**Enter the password and select the checkbox below as per the company's policy.**
<img width="863" height="449" alt="15" src="https://github.com/user-attachments/assets/3b12cc79-0c01-4878-ab73-bac6a0dbed06" />
<img width="1180" height="473" alt="16" src="https://github.com/user-attachments/assets/cac4c504-8809-46b5-bad0-66c5090bc56c" />

## 🔹 Conclusion

In this project, I successfully installed and configured Active Directory Domain Services (AD DS) on Windows Server 2019, transforming the server into a Domain Controller. The setup included creating a new forest, configuring a domain (.local), and establishing a structured Organizational Unit (OU) hierarchy for efficient management of users, groups, computers, and servers.

By implementing Active Directory, the system now provides:

**✅ Centralized Identity & Access Management – A single point for authentication and authorization.**

**✅ Improved Security – Enforced through domain policies, password rules, and Group Policy Objects (GPOs).**

**✅ Efficient Administration – Easier management of large numbers of users and devices through OUs.**

**✅ Scalability & Flexibility – The environment can be expanded to support more users, computers, and even additional domains/forests.**

**This project demonstrates how Active Directory enhances security, productivity, and administrative control in enterprise networks, making it an essential component of modern IT infrastructure. 🚀**





















