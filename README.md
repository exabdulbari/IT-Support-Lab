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
  
## 🧩 2. DNS Configuration

### **Goal**
Configure DNS on the Domain Controller so clients inside **lab.local** can resolve domain resources.

---

### **Steps Completed**
- Installed DNS Server role (automatically with AD DS)
- Verified DNS zones were created:
  - **Forward Lookup Zone:** lab.local
  - **Reverse Lookup Zone:** 192.168.1.x
- Confirmed DC’s DNS settings:
  - Preferred DNS: **192.168.1.10** (itself)
- Configured PC01 to use the DC as its DNS server
- Tested DNS using:
  - `nslookup`
  - Ping by hostname
  - Checking A and PTR records

---

### **Screenshots (Add Yours Below)**
> - DNS Manager (Forward Lookup Zone)  
> - DNS Manager (Reverse Lookup Zone)  
> - nslookup test on PC01  

---

### **What I Learned**
- How DNS integrates with Active Directory  
- Why DC must point DNS to itself  
- How to test DNS using nslookup  
- Why clients must use the Domain Controller for DNS  

## 🧩 3. Client Domain Join (PC01)

### **Goal**
Join a Windows 10 client computer (PC01) to the Active Directory domain **lab.local**.

---

### **Steps Completed**
- Set PC01 network configuration:
  - Joined the same subnet as the Domain Controller
  - Set DNS server to **192.168.1.10**
- Verified network connectivity using:
  - `ping WIN-BPRUP661MS4`
  - `ping lab.local`
- Joined PC01 to the domain:
  - System Properties → Change Settings → Domain: **lab.local**
- Restarted PC01 to apply the domain join
- Logged in using a domain account to verify successful connection

---

### **Screenshots (Add Yours Below)**
> - Network settings on PC01  
> - Domain join confirmation  
> - Login screen showing domain user option  
> - System Properties showing “Domain: lab.local”  

---

### **What I Learned**
- How a Windows client joins a domain  
- Why DNS must point to the Domain Controller  
- Common domain join errors and how to troubleshoot them  
- How to verify domain connectivity

## 🧩 4. Group Policy Management (GPO)
  ### 🧩 4.1 Block USB Storage (GPO)

#### **Goal**
Prevent users from using USB storage devices on domain-joined computers for security and data protection.

---

#### **Steps Completed**
- Opened **Group Policy Management** on the Domain Controller
- Created a new GPO: **Block USB Storage**
- Edited the GPO:
  - Computer Configuration  
    → Administrative Templates  
    → System  
    → Removable Storage Access  
    → Deny All Access (Enabled)
- Linked the GPO to the **PCs OU**
- Forced policy update using:
  - `gpupdate /force` (on PC01)
- Verified USB storage is blocked on PC01

---

#### **Screenshots (Add Yours Below)**
> - GPO settings for Removable Storage Access  
> - GPO link to PCs OU  
> - USB blocked message on PC01  

---

#### **What I Learned**
- How to create and link a GPO  
- How GPO inheritance works  
- Difference between **Computer Configuration** and **User Configuration**  
- How to use `gpupdate /force` to refresh GPO  
- Why organizations block external USB storage  

### 🧩 4.2 Block Control Panel (GPO)

### **Goal**
Prevent users from accessing the Windows Control Panel to avoid unauthorized system changes.

---

### **Steps Completed**
- Opened **Group Policy Management**
- Created or edited GPO: **Block Control Panel**
- Navigated to:
  - User Configuration  
    → Administrative Templates  
    → Control Panel  
- Enabled the policy: **Prohibit access to Control Panel and PC settings**
- Linked the GPO to the **Users OU**
- Ran `gpupdate /force` on PC01
- Logged in as a domain user to verify Control Panel is blocked

---

### **Screenshots (Add Yours Below)**
> - GPO location under User Configuration  
> - Enabled policy  
> - PC01 showing Control Panel blocked  

---

### **What I Learned**
- Difference between **User Configuration** and **Computer Configuration**
- Some settings only apply to users, not computers
- How to apply restrictions based on OU targeting
- How companies prevent unauthorized changes by users
  
  - Drive Mapping
- Shared Folder & NTFS Permissions
- Troubleshooting (GPO, DNS, Time Sync, WinRM)
- Extra IT Support Features (Optional)
  - Printer via GPO
  - Folder Redirection
  - User Logon Scripts
  - Software Deployment via GPO
- Summary of Skills Learned
