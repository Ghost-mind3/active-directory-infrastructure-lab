# 13 - Security Rationale

## Overview

This section explains the reasoning behind the security configurations implemented in this Active Directory lab.

The goal is to move beyond "how it works" and focus on **why these configurations are important**, and what risks they help mitigate.

---

## Workstation Security Baseline (GPO)

### What was done

- Disabled Guest account  
- Restricted insecure logon configurations  
- Managed local administrators using Restricted Groups  

### Why

These settings reduce the attack surface on domain workstations and enforce controlled access.

### Risk if not implemented

- Unauthorized access through default accounts  
- Weak authentication mechanisms  
- Privilege escalation on endpoints  

---

## Privileged Access Management

### What was done

- Separated administrative roles:
  - `it.admin` → Domain administration  
  - `it.support` → Local workstation administration  
- Used security groups:
  - `GG_Domain_Admins`  
  - `GG_Workstation_Local_admins`  

### Why

To enforce the **principle of least privilege** and avoid using highly privileged accounts for daily tasks.

### Risk if not implemented

- Overprivileged accounts  
- Increased attack impact if a credential is compromised  
- Poor access control management  

---

## Windows LAPS

### What was done

- Implemented LAPS to manage local administrator passwords  
- Each workstation has a unique, automatically rotated password  

### Why

To prevent the reuse of local administrator credentials across multiple machines.

### Risk if not implemented

- Lateral movement across the network  
- Full compromise of the environment from a single machine  

---

## Group Policy (GPO)

### What was done

- Created and applied multiple GPOs:
  - Workstation baseline  
  - Audit policy  
  - Admin restrictions  
  - LAPS  

### Why

Group Policy provides centralized configuration and ensures consistent security across all domain systems.

### Risk if not implemented

- Inconsistent configurations  
- Security gaps between machines  
- Difficult administration  

---

## Audit Policy

### What was done

- Enabled advanced audit policies:
  - Logon events  
  - Account management  
  - Privilege use  

### Why

To provide visibility into system activity and detect suspicious behavior.

### Risk if not implemented

- No trace of malicious activity  
- Difficult incident response  
- Lack of monitoring  

---

## Organizational Unit (OU) Structure

### What was done

- Structured the domain using OUs:
  - Employees  
  - Endpoints  
  - Groups  

### Why

To organize resources and apply policies efficiently.

### Risk if not implemented

- Poor policy targeting  
- Administrative complexity  
- Increased configuration errors  

---

## Key Takeaway

Security is not only about configuration, but about **understanding the purpose behind each decision**.

This approach allows:

- Better system design  
- Stronger security posture  
- Easier troubleshooting and improvement  

---

## Conclusion

This lab demonstrates that even a basic Active Directory environment can be significantly improved by applying simple but effective security principles.

Understanding the "why" behind each configuration is essential for both system administration and cybersecurity.
