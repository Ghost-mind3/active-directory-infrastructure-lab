# 🌐 Domain Controller Setup – Windows Server 2019

## 📌 Objective
Install and promote **Windows Server 2019** as a **Domain Controller** with a new Active Directory forest.

---

## 🏢 Domain Information

- **Domain Name:** evilcorp.local  
- **Functional Level:** Windows Server 2019  
- **DNS:** Integrated with Active Directory  

---

## 🔧 Installation Steps

### 1. Install Active Directory Domain Services (AD DS)  
- Open **Server Manager → Add Roles and Features → AD DS**  
- Follow the wizard to install the role  

#### 📷 Screenshots
![AD DS Installation](Images/ADconf.png) 

---

### 2. Promote Server to Domain Controller  
- In **Server Manager → AD DS**, select **Promote this server to a domain controller**  

#### 📷 Screenshots
![AD DS Installation](Images/promoteAD.png) 

---

### 3. Create New Forest  
- Choose **Add a new forest** and enter the **Root Domain Name:** `evilcorp.local`  
- Set the **Forest Functional Level** and **Domain Functional Level** to **Windows Server 2019**  
- Configure the **DSRM password**  

#### 📷 Screenshots
![NEW FORET creation](Images/createForêt.png)  

![NEW FORET creation](Images/createForêt2.png)  

![NEW FORET creation](Images/createForêt3.png) 

![NEW FORET creation](Images/createForêt4.png)  

---

### 4. Reboot Server  
- After promotion, the server will automatically restart  

#### 📷 Screenshots
![AD DS Installation](Images/DCpromote.png)  

---

## ✅ Post-Installation Verification

- **Domain evilcorp.local successfully created**  
- **Static IP configured successfully**  
- **RDP activated** – important for administration and security (remote management, auditing, limiting physical access)  
- **DNS zone automatically created**  
- **SYSVOL and NETLOGON shares verified**  
- **`dcdiag` executed successfully**  

---

## 🔐 RDP Best Practices on Domain Controllers

1. Limit access to **administrators only**  
2. Enable **encryption** for RDP sessions  
3. Use **VPN** if accessing from outside the network  
4. Enable **auditing/logging** of RDP sessions  
5. Avoid using the **default Administrator account** for direct login  

---

## 📝 Next Steps

- Add **users and groups** in Active Directory  
- Configure **Group Policy Objects (GPOs)**  
...

---
## 📷 Screenshots

![AD DS Installation](Images/DCpromote2.png)


