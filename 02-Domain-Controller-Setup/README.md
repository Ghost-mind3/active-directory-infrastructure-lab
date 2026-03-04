# Domain Controller Setup

## 📌 Objective

Install and promote Windows Server 2019 as a Domain Controller.

---

## 🏢 Domain Information

- Domain Name: evilcorp.local
- Functional Level: Windows Server 2019
- DNS: Integrated with Active Directory

---

## 🔧 Installation Steps

1. Install Active Directory Domain Services (AD DS)
   ## 📷 Screenshots
![AD DS Installation](Images/ADconf.png) 

2. Promote server to Domain Controller
## 📷 Screenshots
![AD DS Installation](Images/promoteAD.png) 

3. Create new forest
   ## 📷 Screenshots

![NEW FORET creation](Images/createForêt.png)


![NEW FORET creation](Images/createForêt2.png)

![NEW FORET creation](Images/createForêt3.png)

![NEW FORET creation](Images/createForêt4.png)

4. Reboot server

## 📷 Screenshots

![AD DS Installation](Images/DCpromote.png)

---

## ✅ Verification

- Domain successfully created
- Static IP configureted successsfully
- 
- DNS zone automatically created
- SYSVOL and NETLOGON shares verified
- `dcdiag` executed successfully

## 📷 Screenshots

![AD DS Installation](Images/DCpromote2.png)


