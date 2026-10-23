
# Active Directory & DNS Administration Lab

## 1. Overview

This lab documents Windows Server DNS administration and
Active Directory organizational structure exercises completed
during Cognizant CIS Multicloud technical training.

The activities focused on DNS Server installation, forward and
reverse lookup zones, DNS record management, client-side name
resolution, and logical Active Directory organization.

**Scope:** Guided infrastructure training and capstone lab work.

## 2. Lab Environment

| Component | Environment / Tool |
|---|---|
| Virtualization | VMware Workstation |
| Server OS | Windows Server 2022 |
| Client | Windows workstation |
| Server Role | DNS Server |
| Administration | Server Manager, DNS Manager |
| Directory Management | Active Directory Users and Computers |
| Verification | Command Prompt, `ipconfig`, `nslookup` |

## 3. Assignment Objectives

The capstone covered three assignments:

1. Install and configure the Windows Server DNS role, lookup
   zones, and DNS records.
2. Configure client DNS settings, verify name resolution,
   and compare Windows DNS resolution behavior.
3. Design an Active Directory organizational structure
   and organize user and computer accounts.

---

## 4. Assignment 1 — DNS Server Administration

### Task 1: Install and Configure DNS Server

**Objective:** Enable DNS services on Windows Server for
internal name resolution.

#### Implementation Steps

1. Signed in to Windows Server with administrator credentials.
2. Opened **Server Manager**.
3. Selected **Manage → Add Roles and Features**.
4. Chose **Role-based or feature-based installation**.
5. Selected the target Windows Server.
6. Enabled the **DNS Server** role.
7. Completed the installation wizard.
8. Opened **DNS Manager** to verify the installed role.

**Verification:** The DNS Server role was visible in the
Windows Server administration environment.

### Task 2: Configure Forward and Reverse Lookup Zones

**Objective:** Configure DNS zones for hostname and
IP-address resolution.

#### Forward Lookup Zone

| Setting | Configuration |
|---|---|
| Zone name | `company.local` |
| Zone type | Primary |
| Dynamic updates | Enabled (as recorded in the assignment) |
| Purpose | Resolve hostnames to IP addresses |

#### Reverse Lookup Zone

| Setting | Configuration |
|---|---|
| Network ID | `192.168.1` |
| Address family | IPv4 |
| Purpose | Resolve IP addresses to hostnames |

**Technical Explanation:**

A forward lookup zone stores records such as A and AAAA,
allowing clients to resolve hostnames to IP addresses.

A reverse lookup zone uses PTR records to support
IP-address-to-hostname lookups.

**Note:** The original documentation records dynamic updates
as enabled but does not specify the exact update security mode.

### Task 3: DNS Record Management

**Objective:** Understand and configure common DNS records.

| Record | Function |
|---|---|
| A | Maps a hostname to an IPv4 address |
| AAAA | Maps a hostname to an IPv6 address |
| CNAME | Defines an alias pointing to another DNS name |
| MX | Identifies a domain's mail exchanger and preference |
| PTR | Supports reverse DNS resolution |

#### Documented Example

```text
Hostname: web.company.local
IPv4:     192.168.1.20
Record:   A
```

The assignment also references an MX record with
preference value `10`.

An MX record requires a mail exchanger hostname in addition
to its preference value. The complete target is not recorded
in the source documentation.

**Verification Evidence:** DNS Manager screenshots document
the record-management exercise.

---

## 5. Assignment 2 — Name Resolution

### Task 1: Configure DNS Client Settings

**Objective:** Configure a Windows workstation to use the
internal DNS service.

#### Implementation Steps

1. Opened **Network and Sharing Center**.
2. Selected **Change adapter settings**.
3. Opened the active network adapter's properties.
4. Selected **Internet Protocol Version 4 (TCP/IPv4)**.
5. Opened IPv4 properties.
6. Manually configured the preferred DNS server address.
7. Applied the network settings.

The exact DNS server IP is not recorded in the written
assignment and is therefore not reproduced here.

### Task 2: Verify DNS Name Resolution

**Objective:** Check the client's DNS configuration and
test name resolution.

#### Commands Used

```cmd
ipconfig /all
nslookup company.local
```

**Command Explanation:**

- `ipconfig /all` displays detailed network adapter
  configuration, including configured DNS servers.
- `nslookup company.local` queries DNS for records
  associated with the specified domain name.

#### Documented Result

The original lab report records successful name resolution
using `nslookup`.

The supporting screenshot provides the command-line evidence.

**Verification Scope:** This demonstrates the documented
domain lookup. It does not independently establish that
every forward record, PTR record, or mail record was tested.

### Task 3: Compare Windows DNS Resolution

The assignment included a comparison of name resolution
behavior across Windows versions.

Key concepts covered:

- DNS-based hostname resolution
- Local hosts-file entries
- DNS client caching
- Differences in DNS client capabilities and configuration
- DNS-over-HTTPS support on compatible Windows versions

**Learning Note:** Actual name resolution behavior depends
on operating system version, network configuration, policy,
and application behavior. DNS-over-HTTPS is not universally
enabled across Windows systems.

This comparison was documented as conceptual study rather
than a verified multi-version test.

---

## 6. Assignment 3 — Active Directory Structure

### Task 1: Design a Logical AD Structure

**Objective:** Design a manageable directory structure for
a hypothetical medium-sized organization.

#### Lab Domain

```text
company.local
```

#### Organizational Units

```text
company.local
│
├── HR
├── IT
├── Finance
├── Computers
└── Users
```

The structure separates organizational departments and
account categories.

### Tasks 2 and 3: Create OUs and Organize Accounts

The lab documented OU creation and the organization of
user and computer objects through Active Directory
Users and Computers.

**Administrative Purpose:**

- Organize directory objects logically
- Simplify delegated administration
- Support targeted Group Policy application
- Improve directory navigation and maintenance

**Technical Note:** Organizational Units provide logical
containers within Active Directory. Group Policy Objects
can be linked to appropriate sites, domains, and OUs.

The original screenshots document the OU structure and
account hierarchy.

---

## 7. Verification and Results

| Activity | Verification / Evidence |
|---|---|
| DNS Server installation | Server Manager screenshot |
| Forward/reverse zones | DNS Manager screenshot |
| DNS record management | DNS records screenshot |
| Client DNS configuration | IPv4 settings screenshot |
| Name resolution | `nslookup` command output |
| AD structure | OU structure screenshot |
| User/computer organization | OU hierarchy screenshot |

The evidence demonstrates the documented training
activities. No production deployment or independent
enterprise environment is claimed.

---

## 8. Supporting Evidence

### DNS Server Installation

DNS Server role installation and administrative verification.

![DNS Server Installation](Screenshots/DNS-Server-Installation.png)

### Forward and Reverse Lookup Zones

Configured lookup zones displayed in DNS Manager.

![Forward and Reverse Lookup Zones](Screenshots/Forward-Reverse-Lookup-Zones.png)

### DNS Record Management

DNS records configured during the assignment.

![DNS Records](Screenshots/DNS-Records.png)

### DNS Client Configuration

Windows workstation IPv4 DNS configuration.

![DNS Client Configuration](Screenshots/DNS-Client-Configuration.png)

### Name Resolution Verification

Command Prompt output from the DNS resolution exercise.

![NSLookup Verification](Screenshots/NSLookup-Verification.png)

### Active Directory OU Structure

Logical organizational units created for the lab domain.

![Active Directory OU Structure](Screenshots/AD-OU-Structure.png)

### Active Directory Account Hierarchy

User and computer organization within the directory structure.

![Active Directory OU Hierarchy](Screenshots/AD-OU-inside-Structure.png)

---

## 9. Key Learning Outcomes

- Understood Windows Server DNS role installation and management.
- Practiced forward and reverse lookup zone configuration.
- Explored A, AAAA, CNAME, MX, and reverse DNS concepts.
- Configured Windows client DNS settings.
- Used `ipconfig` and `nslookup` for network verification.
- Understood the relationship between DNS and Active Directory.
- Designed logical Organizational Units.
- Practiced organizing user and computer accounts.
- Improved infrastructure documentation and verification skills.

---

## 10. Lab Summary

This lab was completed as part of the Cognizant CIS
Multicloud technical capstone training.

It covered Windows Server DNS configuration, forward and
reverse lookup zones, DNS record management, client-side
name resolution, and Active Directory organizational
structure.

The documented configuration steps and supporting
screenshots demonstrate the technical activities and
verification performed during the lab.

