# 03 - OU Structure Design

## 📌 Objective

Design and implement a structured Organizational Unit (OU) hierarchy within the domain `evilcorp.local`.

The structure was created to ensure:

- Logical separation of accounts
- Security segmentation
- Proper Group Policy application
- Preparation for future Active Directory penetration testing

---

## 🏢 Domain Structure

The following Organizational Units were created:
evilcorp.local
│
├── OU=Admins
│
├── OU=Employees
│ ├── OU=IT
│ ├── OU=RH
│ └── OU=Finance
│
├── OU=Endpoints
│ ├── OU=Workstations
│ └── OU=Servers
│
└── OU=Groups


---

## 🔐 OU=Admins

This OU contains privileged administrative accounts.

### Purpose:
- Isolate administrative users
- Apply stricter security policies
- Reduce privilege escalation risks
- Follow security best practices

---

## 👨‍💼 OU=Employees

Contains standard domain users divided by department:

- IT
- RH
- Finance

### Purpose:
- Department-based segmentation
- Apply user-based GPOs per department
- Simulate real enterprise structure

---

## 🖥️ OU=Endpoints

Contains all domain-joined machines.

### Sub-OUs:
- Workstations (Windows 10 clients)
- Servers

### Purpose:
- Apply computer-based GPOs
- Separate workstation policies from server policies
- Enforce security baseline at machine level

---

## 👥 OU=Groups

Contains all security groups used for:

- Role-based access control
- Secondary administrative privileges
- Resource access management
- ...

This OU supports proper implementation of access control models such as AGDLP.

---

## 🔧 Implementation Notes

- "Protect object from accidental deletion" enabled on critical OUs
- Advanced Features enabled in Active Directory Users and Computers
- Structure created before user and group deployment

---

## 📷 Screenshots

![Full OU Structure](Images/createUO3.png)
![Employees OU](images/createUO2.png)
![Endpoints OU](images/createUO3(2).png)

---

## 🧠 Design Rationale

This OU hierarchy ensures:

- Clear separation of privilege levels
- Proper GPO targeting
- Scalability for future expansion
- Preparation for controlled security testing
