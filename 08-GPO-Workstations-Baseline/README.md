# 08 - Workstation Security Baseline (GPO)

## Overview

This step focuses on creating and configuring a **baseline Group Policy Object (GPO)** for domain workstations.  
The objective is to enforce essential security settings and centralized administration across all client machines within the domain.

The policy is applied to the **Workstations Organizational Unit**, ensuring consistent configuration for all domain-joined workstations.

---

## Target Scope

The GPO is linked to the following Organizational Unit:

```
evilcorp.local
└── OU=Endpoints
    └── OU=Workstations
```

All computers placed inside this OU automatically receive the security configuration defined by the policy.

---

## GPO Creation Procedure

The policy was created using **Group Policy Management Console (GPMC)**.

1. Open **Group Policy Management**
2. Navigate to:

```
Forest: evilcorp.local
└── Domains
    └── evilcorp.local
        └── OU=Endpoints
            └── OU=Workstations
```

3. Right-click **OU=Workstations**
4. Select **Create a GPO in this domain, and Link it here**
5. Name the policy:

```
GPO-Workstation-Baseline
```

---

## Security Configuration

Security settings were configured under:

```
Computer Configuration
└── Policies
    └── Windows Settings
        └── Security Settings
```

The baseline includes several controls designed to improve workstation security.

---

## Guest Account Hardening

The built-in **Guest account** was disabled.

Disabling this account prevents anonymous or unauthorized access attempts that could otherwise be exploited within the environment.

---

## Secure Logon Configuration

Insecure logon mechanisms were disabled in order to enforce stronger authentication standards within the domain environment.

This reduces the risk of authentication abuse and improves the overall security posture of domain workstations.

---

## Restricted Groups Configuration

To centralize administrative privilege management, **Restricted Groups** were configured.

The following Active Directory security group is used:

```
GG_Workstation_Local-admins
```

This group is automatically added to the **local Administrators group** on all domain workstations.

### Benefits

- Centralized management of administrator privileges
- Consistent privilege assignment across all workstations
- Reduced risk of privilege misuse
- Simplified administrative management

Using **security groups instead of individual user accounts** follows standard enterprise best practices.

---

## Screenshots

Configuration screenshots are available in the **Images** directory.

Examples include:

- GPO creation
- Policy configuration
- Restricted groups setup

---

## Key Takeaways

- Group Policy provides centralized configuration management in Active Directory environments.
- Applying policies to Organizational Units ensures structured and scalable administration.
- Disabling unnecessary accounts reduces potential attack surfaces.
- Managing administrative access through security groups improves operational security.
