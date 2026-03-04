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
2. Promote server to Domain Controller
3. Create new forest
4. Set DSRM password
5. Reboot server

---

## 📷 Screenshots

(Add promotion wizard screenshots here)

Example:

![AD DS Installation](images/adds-install.png)
![Domain Promotion](images/domain-promotion.png)

---

## ✅ Verification

- Domain successfully created
- DNS zone automatically created
- SYSVOL and NETLOGON shares verified
- `dcdiag` executed successfully
