# 06 - Windows 10 Domain Join

## 📌 Objective

Join a Windows 10 client machine to the domain `evilcorp.local` and ensure proper integration into the Active Directory structure.

---

## 🖥️ Environment Details

- Domain Controller: 192.168.32.130
- Domain: evilcorp.local
- Client Machine: Windows 10
- Client IP: 192.168.32.131
- Network: 192.168.32.0/24

---

## 🌐 Step 1 - Client Network Configuration

The Windows 10 client was configured with:

- Static IP address: 192.168.32.131
- Subnet mask: 255.255.255.0
- Preferred DNS server: 192.168.32.130

## 📷 Screenshots
![clientnetconf](Images/netconfClient.png)
⚠️ Important:  
The DNS server must point to the Domain Controller to allow domain resolution.

Without correct DNS configuration, the domain join will fail.

## 🔎 Step 2 - DNS Configuration
![dnsconfig](Images/DnsConf.png)
![dnsconfig](Images/DnsConf2.png)
![dnsconfig](Images/DnsConf3.png)
![dnsconfig](Images/DnsConf4.png)

## 🔐 Step 3 - Join the Domain

Procedure followed:

1. Open Windows System Files and click on 'My PC'
   ![joindc-01](Images/JoinDC.png)
2. Click 'property'
   ![joindc-02](Images/JoinDC2.png)
4. Click on 'advance setting system'
   ![joindc-03](Images/JoinDC3.png)
5. Click on 'Computer Name'
   ![joindc-04](Images/JoinDC4.png)
6. Click on 'Modify'
   ![joindc-05](Images/JoinDC5.png)
7. Enter the Domain Name evilcorp.local
   ![joindc-06](Images/JoinDC6.png)
8. Restart the machine
    ![joindc-07](Images/JoinDC7.png)
   ![joindc-08](Images/JoinDC8.png)

Upon successful authentication, the machine becomes a domain member.
![joindc-07](Images/JoinDC7.png)
![joindc-09](Images/JoinDC9.png)


## ✅ Step 4 - Verification in Active Directory

After reboot:

- Open Active Directory Users and Computers
- Confirm the computer object appears under:
  ![joindc-10](Images/JoinDC10.png)

  This confirms the machine has successfully joined the domain.

  ## 🧠 Why Moving the Computer Object Is Important

By default, new domain-joined machines are placed inside the "Computers" container.

However:

- The default container is not an Organizational Unit
- Group Policies cannot be directly linked there
- It does not follow structured administrative design

Moving the machine into:

Endpoints → Workstations

ensures proper policy targeting and organizational consistency.

