## 📘 IT Support Lab Documentation

### Table of Contents
## 🧩 1. Active Directory & Domain Setup
    ### **Goal**
    Set up a Windows Server 2022 machine as a Domain Controller for the domain **lab.local**.
    
    ---
    
    ### **Steps Completed**
    - Installed Windows Server 2022  
    - Assigned static IP address: **192.168.1.10**  
    - Installed **Active Directory Domain Services (AD DS)**  
    - Promoted the server to a **Domain Controller**  
    - Created a new domain: **lab.local**  
    - Verified Domain Controller health using:
      - `dcdiag`
      - Server Manager
      - Event Viewer
    
    ---
    
    ### **Screenshots (Add Yours Below)**
    > - AD DS installation  
    > - Domain promotion  
    > - Server Manager dashboard (Domain Services installed)
    
    ---
    
    ### **What I Learned**
    - How a domain works  
    - Why a static IP is required  
    - What a Domain Controller does  
    - Basic AD DS architecture
- 
- DNS Configuration
- Client Domain Join (PC01)
- Group Policy Management (GPO)
  - Block USB
  - Block Control Panel
  - Drive Mapping
- Shared Folder & NTFS Permissions
- Troubleshooting (GPO, DNS, Time Sync, WinRM)
- Extra IT Support Features (Optional)
  - Printer via GPO
  - Folder Redirection
  - User Logon Scripts
  - Software Deployment via GPO
- Summary of Skills Learned
