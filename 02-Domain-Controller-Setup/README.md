# Domain Controller Setup

## 📌 Objective

promote Windows Server 2019 as a Domain Controller.

---

## 🏢 Domain Information

- Domain Name: evilcorp.local
- Functional Level: Windows Server 2019
- DNS: Integrated with Active Directory

---

## 🔧 Installation Steps

1. Promote server to Domain Controller
2. Create new forest
3. Set DSRM password
4. Reboot server

---

## 📷 Screenshots

![Domain Promotion](images/domain-promotion.png)

---

## ✅ Verification

- Domain successfully created
- DNS zone automatically created
- SYSVOL and NETLOGON shares verified
- `dcdiag` executed successfully
