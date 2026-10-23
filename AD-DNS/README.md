
# 🖥️ Active Directory & DNS Administration Lab

## 📌 1. Overview

This lab documents Windows Server DNS administration and Active Directory organizational structure exercises completed during **Cognizant CIS Multicloud technical training**.

The activities focused on DNS Server installation, forward and reverse lookup zones, DNS record management, client-side name resolution, and logical Active Directory organization.

The lab combined practical configuration, verification, and infrastructure administration concepts.

## 🛠️ 2. Lab Environment

| Component | Environment / Tool |
|---|---|
| Virtualization | VMware Workstation |
| Server OS | Windows Server 2022 |
| Client | Windows workstation |
| Server Role | DNS Server |
| Administration | Server Manager, DNS Manager |
| Directory Management | Active Directory Users and Computers |
| Verification | Command Prompt, `ipconfig`, `nslookup` |

## 🎯 3. Assignment Objectives

The capstone covered three assignments:

1. Install and configure the Windows Server DNS role, forward and reverse lookup zones, and DNS records.
2. Configure client DNS settings, verify name resolution, and compare Windows DNS resolution behavior.
3. Design an Active Directory organizational structure and organize user and computer accounts.

---

## 🌐 4. Assignment 1 — DNS Server Administration

### Task 1: Install and Configure DNS Server

**Objective:** Enable DNS services on Windows Server for internal name resolution.

#### Implementation Steps

1. Signed in to Windows Server with administrator credentials.
2. Opened **Server Manager**.
3. Selected **Manage → Add Roles and Features**.
4. Chose **Role-based or feature-based installation**.
5. Selected the target Windows Server.
6. Enabled the **DNS Server** role.
7. Completed the installation wizard.
8. Opened **DNS Manager** to verify the installed role.

**Verification:** The DNS Server role was visible in the Windows Server administration environment.

### Task 2: Configure Forward and Reverse Lookup Zones

**Objective:** Configure DNS zones for hostname and IP-address resolution.

#### Forward Lookup Zone

| Setting | Configuration |
|---|---|
| Zone name | `company.local` |
| Zone type | Primary |
| Dynamic updates | Enabled, as recorded in the assignment |
| Purpose | Resolve hostnames to IP addresses |

#### Reverse Lookup Zone

| Setting | Configuration |
|---|---|
| Network ID | `192.168.1` |
| Address family | IPv4 |
| Purpose | Resolve IP addresses to hostnames |

#### Technical Explanation

A forward lookup zone stores records such as A and AAAA, allowing clients to resolve hostnames to IP addresses.

A reverse lookup zone uses PTR records to support IP-address-to-hostname resolution.

The assignment covered dynamic DNS updates as part of the forward lookup zone configuration.

### Task 3: DNS Record Management

**Objective:** Understand and configure common DNS records.

| Record | Function |
|---|---|
| A | Maps a hostname to an IPv4 address |
| AAAA | Maps a hostname to an IPv6 address |
| CNAME | Defines an alias pointing to another DNS name |
| MX | Identifies a domain's mail exchanger and preference |
| PTR | Supports reverse DNS resolution |

#### Documented A Record Example

```text
Hostname: web.company.local
IPv4:     192.168.1.20
Record:   A
```

#### MX Record

An MX record identifies the mail exchanger responsible for receiving email for a domain.

The assignment covered MX record configuration, including a priority value of `10`.

MX records use a mail exchanger hostname together with a preference value.

**Verification Evidence:** DNS Manager screenshots document the DNS record-management exercise.

---

## 🔍 5. Assignment 2 — DNS Client Configuration & Name Resolution

### Task 1: Configure DNS Client Settings

**Objective:** Configure a Windows workstation to use the internal DNS service.

#### Implementation Steps

1. Opened **Network and Sharing Center**.
2. Selected **Change adapter settings**.
3. Opened the active network adapter's properties.
4. Selected **Internet Protocol Version 4 (TCP/IPv4)**.
5. Opened IPv4 properties.
6. Configured the preferred DNS server address.
7. Applied the network settings.

This configuration allows the workstation to direct DNS queries to the specified DNS server.

### Task 2: Verify DNS Name Resolution

**Objective:** Inspect the client's DNS configuration and test domain name resolution.

#### Commands Used

```cmd
ipconfig /all
nslookup company.local
```

#### Command Explanation

| Command | Purpose |
|---|---|
| `ipconfig /all` | Displays detailed network adapter configuration, including DNS server settings |
| `nslookup company.local` | Queries DNS for records associated with the specified domain name |

#### Documented Result

The original lab report records successful name resolution using `nslookup`.

The supporting command-line screenshot documents the DNS verification exercise.

This demonstrates the domain lookup performed during the lab.

### Task 3: Compare DNS Resolution Across Windows Versions

The assignment included a comparison of DNS resolution concepts across Windows client and server operating systems.

| Platform | DNS Concepts Reviewed |
|---|---|
| Windows 7 | DNS client configuration, HOSTS file, and DNS caching |
| Windows 10/11 | DNS client configuration, caching, and modern DNS security features |
| Windows Server | DNS client functionality and DNS Server role administration |

#### Additional Concepts Studied

- DNS-based hostname resolution
- Local HOSTS file entries
- DNS client caching
- DNS configuration differences
- DNS security and DNS-over-HTTPS concepts

DNS resolution behavior and supported security features depend on the operating system version, network configuration, and applicable policies.

DNS-over-HTTPS is not universally enabled across Windows operating systems.

This comparison was part of the conceptual study included in the assignment.

---

## 🏢 6. Assignment 3 — Active Directory Organizational Structure

### Task 1: Design a Logical AD Structure

**Objective:** Design a manageable Active Directory structure for a hypothetical medium-sized organization.

#### Lab Domain

```text
company.local
```

#### Organizational Unit Structure

```text
company.local
│
├── HR
├── IT
├── Finance
├── Computers
└── Users
```

The structure organizes directory objects into departments and account categories.

### Task 2: Create Organizational Units

The lab covered creating Organizational Units (OUs) using Active Directory Users and Computers.

#### OUs Included

| Organizational Unit | Purpose |
|---|---|
| HR | Organize Human Resources accounts |
| IT | Organize Information Technology accounts |
| Finance | Organize Finance department accounts |
| Computers | Organize computer objects |
| Users | Organize user accounts |

Organizational Units provide logical containers for managing directory objects.

### Task 3: Organize User and Computer Accounts

The assignment documented organizing user and computer objects within the Active Directory structure.

#### Administrative Benefits

- Logical organization of directory objects
- Simplified directory navigation
- Easier administration of departmental accounts
- Support for delegated administration
- Support for targeted Group Policy application

#### Technical Explanation

Active Directory Organizational Units help administrators organize and manage directory objects.

Group Policy Objects can be linked to appropriate sites, domains, and OUs to apply configuration policies.

The screenshots document the OU structure and account hierarchy created during the lab.

---

## ✅ 7. Verification & Technical Results

| Activity | Verification / Evidence |
|---|---|
| DNS Server installation | Server Manager screenshot |
| Forward and reverse lookup zones | DNS Manager screenshot |
| DNS record management | DNS records screenshot |
| Client DNS configuration | IPv4 settings screenshot |
| Name resolution | `nslookup` command output |
| Active Directory structure | OU structure screenshot |
| User and computer organization | OU hierarchy screenshot |

The documented activities demonstrate Windows Server DNS administration, client-side DNS verification, and logical Active Directory organization.

---

## 📸 8. Supporting Evidence

### 8.1 DNS Server Installation

DNS Server role installation and administrative verification.

![DNS Server Installation](Screenshots/DNS-Server-Installation.png)

### 8.2 Forward and Reverse Lookup Zones

Configured forward and reverse lookup zones displayed in DNS Manager.

![Forward and Reverse Lookup Zones](Screenshots/Forward-Reverse-Lookup-Zones.png)

### 8.3 DNS Record Management

DNS records configured during the assignment.

![DNS Records](Screenshots/DNS-Records.png)

### 8.4 DNS Client Configuration

Windows workstation IPv4 DNS configuration.

![DNS Client Configuration](Screenshots/DNS-Client-Configuration.png)

### 8.5 Name Resolution Verification

Command Prompt output from the DNS resolution exercise.

![NSLookup Verification](Screenshots/NSLookup-Verification.png)

### 8.6 Active Directory OU Structure

Logical Organizational Units created for the lab domain.

![Active Directory OU Structure](Screenshots/AD-OU-Structure.png)

### 8.7 Active Directory Account Hierarchy

User and computer organization within the directory structure.

![Active Directory OU Hierarchy](Screenshots/AD-OU-inside-Structure.png)

---

## 🧠 9. Key Learning Outcomes

- Practiced Windows Server DNS role installation and management.
- Configured forward and reverse lookup zones.
- Explored A, AAAA, CNAME, MX, and PTR record concepts.
- Configured Windows client DNS settings.
- Used `ipconfig` and `nslookup` for network verification.
- Understood DNS resolution across Windows operating systems.
- Explored the relationship between DNS and Active Directory.
- Designed a logical Active Directory OU structure.
- Practiced organizing user and computer accounts.
- Understood how OUs support administration and Group Policy.
- Strengthened infrastructure documentation and verification skills.

---

## 🚀 10. Lab Summary

This lab was completed as part of the Cognizant CIS Multicloud technical capstone training.

It covered Windows Server DNS configuration, forward and reverse lookup zones, DNS record management, client-side name resolution, and Active Directory organizational structure.

The documented configuration steps and supporting screenshots demonstrate the technical activities and verification performed during the lab.

These exercises strengthened foundational skills relevant to Windows Server administration, infrastructure management, cloud operations, and system administration.
