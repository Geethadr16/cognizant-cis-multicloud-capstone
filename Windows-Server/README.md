
# 🖥️ Windows Server Administration | Infrastructure & Security Lab

## 📌 1. Overview

This module documents Windows Server administration exercises completed during the **Cognizant CIS Multicloud technical capstone training program**.

The assignments focused on user account administration, password and account lockout policies, Windows performance monitoring, event log analysis, network interface configuration, NIC Teaming, routing, Windows Server Update Services (WSUS), Windows Firewall, printer sharing, and security policy management.

The lab introduced core Windows Server administration tasks used in enterprise IT infrastructure, system administration, and infrastructure operations.

**Assignments Covered:**

1. **User Account Management & System Monitoring:** Local and domain accounts, password policies, account lockout, Task Manager, Performance Monitor, Event Viewer, Custom Views, and Resource Monitor.
2. **Network & Security Configuration:** NIC configuration, NIC Teaming, routing, WSUS, Windows Firewall, network printer services, and security policies.

## 🛠️ 2. Lab Environment & Technologies

| Component | Technology / Tool |
|---|---|
| Operating System | Windows Server |
| Directory Administration | Active Directory Users and Computers (ADUC) |
| Local Account Management | Computer Management |
| Policy Administration | Group Policy Editor |
| Process Monitoring | Task Manager |
| Performance Monitoring | Performance Monitor |
| Event Log Analysis | Event Viewer |
| Resource Monitoring | Resource Monitor |
| Network Configuration | TCP/IP, DNS, Default Gateway |
| Network Redundancy | NIC Teaming |
| Routing | Windows IP Routing Configuration |
| Update Management | Windows Server Update Services (WSUS) |
| Firewall Administration | Windows Defender Firewall |
| Printer Management | Print and Document Services |
| Security Administration | Windows Security Policies |

## 🎯 3. Technical Objectives

- Create and manage local Windows user accounts.
- Create and administer domain user accounts using ADUC.
- Configure password complexity and expiration policies.
- Implement account lockout settings.
- Monitor processes and system resource consumption.
- Use Performance Monitor to inspect system performance.
- Analyze Windows application, system, and security event logs.
- Create Custom Views in Event Viewer.
- Use Resource Monitor to investigate resource activity.
- Configure static IP addresses and DNS settings.
- Understand NIC Teaming for network redundancy.
- Review default gateway and static routing configuration.
- Install and configure WSUS.
- Manage inbound and outbound Windows Firewall rules.
- Configure network printer sharing.
- Understand user access controls and basic security policies.

---

## 👥 4. Assignment 1 — User Account Management & System Monitoring

### 4.1 Task 1 — Create Local & Domain User Accounts

**Objective:** Understand user account administration in standalone and domain-managed Windows environments.

The assignment covered two account types:

- Local user accounts.
- Active Directory domain user accounts.

#### Local User Account Management

Local user accounts are managed on an individual Windows computer.

**Documented Implementation Steps:**

1. Opened **Computer Management**.
2. Navigated to **Local Users and Groups**.
3. Selected the Users container.
4. Created local user accounts.
5. Reviewed the account configuration.

**Administrative Uses:**

- Managing access to individual systems.
- Creating accounts for local administration.
- Assigning permissions.
- Supporting account maintenance.

#### Domain User Account Management

Domain user accounts are centrally managed through Active Directory Domain Services (AD DS).

**Documented Implementation Steps:**

1. Opened **Active Directory Users and Computers (ADUC)**.
2. Navigated to the appropriate domain or Organizational Unit.
3. Created domain user accounts.
4. Reviewed account details.
5. Verified the account's presence in Active Directory.

#### Local vs. Domain Accounts

| Feature | Local Account | Domain Account |
|---|---|---|
| Management | Individual computer | Active Directory |
| Authentication | Local system | Domain infrastructure |
| Administration | Local administrators | Authorized domain administrators |
| Typical Use | Standalone or local access | Enterprise identity management |
| Policy Scope | Local policies | Applicable domain and Group Policies |

### 4.2 Task 2 — Configure Password Policies

**Objective:** Understand how password policies support account security.

The original assignment documents configuration through Group Policy.

**Documented Activities:**

1. Opened Group Policy Editor.
2. Navigated to Password Policy.
3. Configured password complexity requirements.
4. Configured password expiration settings.
5. Reviewed the policy configuration.

#### Common Password Policy Settings

| Setting | Purpose |
|---|---|
| Minimum Password Length | Defines minimum password characters |
| Password Complexity | Requires configured complexity rules |
| Maximum Password Age | Controls password expiration |
| Minimum Password Age | Limits immediate password reuse |
| Password History | Restricts reuse of previous passwords |

#### Group Policy Navigation

A commonly used policy location is:

```text
Computer Configuration
    |
    +-- Policies
        |
        +-- Windows Settings
            |
            +-- Security Settings
                |
                +-- Account Policies
                    |
                    +-- Password Policy
```

The exact policy interface depends on whether the configuration is performed through local policy or domain Group Policy.

### 4.3 Task 3 — Configure Account Lockout Policies

**Objective:** Configure account lockout behavior following unsuccessful authentication attempts.

The assignment documented configuring account lockout settings.

#### Common Account Lockout Settings

| Setting | Purpose |
|---|---|
| Account Lockout Threshold | Number of failed attempts before lockout |
| Account Lockout Duration | Time the account remains locked |
| Reset Account Lockout Counter After | Time after which the failed-attempt counter resets |

**Conceptual Authentication Workflow:**

```text
             User Login Attempt
                     |
                     v
            Validate Credentials
                     |
              +------+------+
              |             |
              v             v
           Success        Failure
              |             |
              v             v
          Grant Access   Increase Failed
                         Attempt Counter
                              |
                              v
                      Threshold Reached?
                         /         \
                       No           Yes
                       |             |
                       v             v
                     Retry       Account
                                  Lockout
```

Account lockout policies help limit repeated password-guessing attempts but must be configured carefully to avoid unnecessary account disruption.

### 4.4 Task 4 — Monitor User Activity with Task Manager

**Objective:** Monitor running processes and resource consumption.

The original assignment used Windows Task Manager.

**Activities Performed:**

- Reviewed running processes.
- Monitored CPU utilization.
- Monitored memory utilization.
- Inspected resource usage associated with processes.

#### Task Manager Monitoring Areas

| Area | Information |
|---|---|
| Processes | Running applications and background processes |
| Performance | CPU, memory, disk, and network resource activity |
| Users | Resource usage associated with signed-in users |
| Details | Detailed process information |
| Services | Windows service information |

**Administrative Applications:**

- Identifying resource-intensive processes.
- Investigating application performance issues.
- Reviewing active processes.
- Supporting basic system troubleshooting.

### 4.5 Task 5 — Configure Performance Monitor

**Objective:** Monitor system performance through Windows performance counters.

The assignment documented adding counters for:

- CPU usage.
- Memory usage.
- Disk activity.

#### Performance Monitoring Concepts

| Resource | Example Counter | Purpose |
|---|---|---|
| CPU | `Processor(_Total)\% Processor Time` | Observe processor utilization |
| Memory | `Memory\Available MBytes` | Observe available physical memory |
| Disk | `PhysicalDisk(_Total)\% Disk Time` | Observe disk activity |

The counter names above are illustrative Windows performance counters; the original report does not specify the exact counter names selected.

#### Monitoring Workflow

```text
          Windows Server
                |
                v
        Performance Monitor
                |
                v
         Select Counters
                |
        +-------+-------+
        |       |       |
        v       v       v
       CPU    Memory   Disk
        |       |       |
        +-------+-------+
                |
                v
       Analyze Performance
```

**Administrative Uses:**

- Identifying performance bottlenecks.
- Observing system resource trends.
- Supporting capacity planning.
- Troubleshooting resource-related issues.

### 4.6 Task 6 — Windows Event Log Monitoring

**Objective:** Analyze Windows event logs for system administration and troubleshooting.

The assignment covered Event Viewer and three log categories.

#### Windows Event Logs

| Log | Purpose |
|---|---|
| Application | Records application-generated events |
| Security | Records security and audit events |
| System | Records operating system and service events |

#### Documented Activities

1. Opened Event Viewer.
2. Reviewed Application logs.
3. Reviewed Security logs.
4. Reviewed System logs.
5. Inspected recorded events.

#### Event Log Analysis

Windows event records can provide information such as:

- Event ID.
- Event source.
- Severity level.
- Date and time.
- Event description.

These details help administrators investigate system failures, application issues, and security-related activity.

### 4.7 Task 7 — Create Custom Event Views

**Objective:** Filter Windows event logs to display events matching selected criteria.

The original report documents creating Custom Views for specific event IDs.

#### Documented Workflow

1. Opened Event Viewer.
2. Selected **Create Custom View**.
3. Chose relevant event logs.
4. Specified event filtering criteria.
5. Entered the required Event IDs.
6. Saved the Custom View.
7. Reviewed matching events.

#### Benefits

- Simplifies event investigation.
- Reduces irrelevant log information.
- Supports targeted troubleshooting.
- Improves efficiency when reviewing recurring events.

### 4.8 Task 8 — Resource Monitor

**Objective:** Inspect detailed resource consumption across running processes.

The assignment covered:

- Disk utilization.
- Network activity.
- Memory usage per process.

#### Resource Monitor Components

| Component | Monitoring Purpose |
|---|---|
| CPU | Process and thread-related CPU activity |
| Memory | Physical memory usage and allocation |
| Disk | Disk I/O and file activity |
| Network | Network connections and traffic |

**Administrative Uses:**

- Identifying processes generating high disk activity.
- Investigating network usage.
- Reviewing process memory consumption.
- Supporting performance troubleshooting.

### Assignment 1 — Technical Outcome

Practiced Windows user administration, password and account lockout configuration, process monitoring, performance counter inspection, event log analysis, Custom Views, and resource monitoring.

---

## 🌐 5. Assignment 2 — Network & Security Configuration

### 5.1 Task 1 — Configure Network Interface Cards

**Objective:** Configure Windows Server network settings.

The assignment documented:

- Static IP address configuration.
- DNS server configuration.

#### Configuration Workflow

1. Opened network adapter settings.
2. Selected the required network interface.
3. Opened IPv4 properties.
4. Configured the static IP address.
5. Configured the subnet mask or prefix.
6. Specified the default gateway where required.
7. Configured DNS server addresses.
8. Applied the network configuration.

#### Network Configuration Parameters

| Parameter | Purpose |
|---|---|
| IP Address | Identifies the network interface |
| Subnet Mask / Prefix | Defines the local IP network |
| Default Gateway | Routes traffic toward other networks |
| DNS Server | Resolves hostnames to IP addresses |

**Conceptual Architecture:**

```text
           Windows Server
                 |
                 v
          Network Adapter
                 |
          TCP/IP Settings
                 |
        +--------+--------+
        |        |        |
        v        v        v
     IP Address  DNS    Gateway
                 |
                 v
          Network Access
```

### 5.2 Task 2 — Configure NIC Teaming

**Objective:** Understand network interface redundancy and traffic distribution.

NIC Teaming combines supported network adapters into a logical team.

The assignment documents enabling NIC Teaming for redundancy and load-balancing concepts.

#### NIC Teaming Architecture

```text
              Windows Server
                    |
                    v
               NIC Team
               /      \
              v        v
           NIC 1      NIC 2
              |        |
              v        v
          Network Connectivity
```

#### Benefits of NIC Teaming

- Redundant network connectivity.
- Improved availability during supported adapter failures.
- Potential traffic distribution.
- Reduced dependency on a single network adapter.

**Technical Note:**

The exact teaming behavior depends on the operating system, team configuration, network adapters, and switch configuration.

The assignment documents NIC Teaming configuration, but it does not provide measured throughput or verified failover results.

### 5.3 Task 3 — Configure IP Addressing & Routing

**Objective:** Understand IP addressing and network routing in Windows Server.

The original assignment documents:

- Gateway configuration.
- Static routing entries.
- Routing table inspection.

#### Default Gateway

A default gateway provides a route for traffic whose destination is outside the local network when no more specific route applies.

#### Static Routes

Static routes allow administrators to specify paths to particular networks.

**Illustrative Windows Command:**

```cmd
route print
```

Displays the current IPv4 and IPv6 routing tables.

**Illustrative Static Route Syntax:**

```cmd
route add <destination-network> mask <subnet-mask> <gateway-ip>
```

The syntax above is provided as a technical reference; the source report does not specify the exact route values configured.

#### Routing Workflow

```text
             Windows Server
                   |
                   v
           Destination Address
                   |
                   v
             Routing Table
                   |
          +--------+--------+
          |                 |
          v                 v
      Local Route      Gateway Route
          |                 |
          v                 v
     Local Network     Remote Network
```

### 5.4 Task 4 — Install & Configure WSUS

**Objective:** Understand centralized Windows update administration.

Windows Server Update Services (WSUS) supports centralized management of Microsoft updates in compatible Windows environments.

#### Documented Activities

1. Installed the WSUS server role.
2. Configured update synchronization.
3. Reviewed available updates.
4. Approved updates.

#### WSUS Administration Concepts

| Component | Purpose |
|---|---|
| WSUS Server | Centrally manages update metadata and approvals |
| Synchronization | Retrieves update information from a configured source |
| Update Approval | Determines which updates are approved for deployment |
| Client Computers | Receive updates according to their configuration and applicable policies |
| Reporting | Provides information about update status |

#### Conceptual WSUS Architecture

```text
           Microsoft Update
                  |
                  v
              WSUS Server
                  |
          Update Management
                  |
           +------+------+
           |             |
           v             v
        Client A      Client B
```

#### Administrative Benefits

- Centralized update approvals.
- More controlled patch deployment.
- Improved update visibility.
- Support for enterprise patch management workflows.

**Verification Scope:**

The report documents WSUS installation, synchronization configuration, and update approval activities. It does not independently establish successful installation of approved updates on every client.

### 5.5 Task 5 — Configure Windows Firewall

**Objective:** Manage network traffic using Windows Firewall rules.

The assignment covered configuring:

- Inbound firewall rules.
- Outbound firewall rules.

#### Inbound Rules

Inbound rules control applicable network traffic entering the system.

#### Outbound Rules

Outbound rules control applicable network traffic leaving the system.

#### Firewall Rule Parameters

| Parameter | Purpose |
|---|---|
| Direction | Inbound or outbound |
| Action | Allow or block |
| Protocol | TCP, UDP, or another supported protocol |
| Port | Applicable network port |
| Profile | Domain, Private, or Public |
| Scope | Applicable local or remote addresses |

#### Firewall Configuration Workflow

1. Opened Windows Firewall administration.
2. Selected the required rule direction.
3. Created or reviewed a firewall rule.
4. Configured the applicable rule settings.
5. Applied the rule.
6. Reviewed the resulting firewall configuration.

**Security Principle:**

Firewall rules should allow only the network traffic required for authorized services and applications.

### 5.6 Task 6 — Configure Network Printer Services

**Objective:** Understand centralized printer sharing and network printer administration.

The original capstone documents installing the print server role and sharing printers across the network.

#### Documented Activities

1. Installed the printer server role.
2. Configured printer sharing.
3. Reviewed network printer access.

#### Conceptual Architecture

```text
              Client Computers
                 /       \
                v         v
               Network Printer
                    Server
                      |
                      v
                 Shared Printer
```

#### Administrative Benefits

- Centralized printer administration.
- Shared printer access.
- Easier printer configuration.
- Support for controlled access to printing resources.

### 5.7 Task 7 — Implement Basic Network Security Policies

**Objective:** Understand how Windows security settings protect infrastructure resources.

The assignment covered:

- Firewall policies.
- User access controls.
- Restricted services.

#### Security Policy Areas

| Security Area | Purpose |
|---|---|
| Firewall Policies | Control permitted network traffic |
| User Access Control | Restrict access to authorized users |
| Service Restrictions | Limit unnecessary or unauthorized services |
| Password Policies | Strengthen account authentication requirements |
| Account Lockout | Limit repeated failed authentication attempts |

#### Security Administration Workflow

```text
             Security Requirements
                      |
                      v
              Configure Policies
                      |
          +-----------+-----------+
          |           |           |
          v           v           v
       Firewall     User Access   Services
          |           |           |
          +-----------+-----------+
                      |
                      v
              Review Configuration
```

### Assignment 2 — Technical Outcome

Practiced Windows network configuration, NIC Teaming, routing, WSUS administration, Windows Firewall management, printer sharing, and basic infrastructure security policies.

---

## 🔧 6. Windows Server Administration Tools

| Tool | Administrative Purpose |
|---|---|
| Computer Management | Manage local users and system components |
| Active Directory Users and Computers | Administer domain users and directory objects |
| Group Policy Editor | Configure applicable policy settings |
| Task Manager | Inspect running processes and resource usage |
| Performance Monitor | Monitor system performance counters |
| Event Viewer | Investigate Windows event logs |
| Resource Monitor | Analyze CPU, memory, disk, and network activity |
| Network Connections | Configure network adapters |
| NIC Teaming | Manage supported network adapter teams |
| WSUS Console | Manage update synchronization and approvals |
| Windows Firewall | Configure network traffic rules |
| Print Management | Manage supported print services and printers |

---

## 🛡️ 7. Infrastructure Administration & Security Concepts

### 7.1 Identity & Access Management

Windows Server uses local and domain identities to control access to resources.

The assignment introduced:

- Account creation.
- Password policies.
- Account lockout.
- Access control.
- Directory administration.

### 7.2 Performance & Availability Monitoring

Monitoring tools help administrators identify performance problems and investigate resource usage.

**Tools Covered:**

- Task Manager.
- Performance Monitor.
- Event Viewer.
- Resource Monitor.

### 7.3 Network Availability

NIC Teaming and routing configuration support network connectivity and infrastructure operations.

NIC Teaming can provide adapter-level redundancy in supported configurations.

### 7.4 Patch Management

WSUS supports centralized Windows update administration.

Patch management also requires appropriate testing, deployment planning, and verification.

### 7.5 Host Security

Windows Firewall, account policies, and service restrictions help reduce unnecessary access and exposure.

These controls are part of a broader Windows Server security approach.

---

## ✅ 8. Verification & Technical Results

| Assignment | Technical Activity | Evidence |
|---|---|---|
| User Management | Local and domain user creation | User management screenshot |
| Password Policies | Complexity and expiration settings | Policy screenshot |
| Account Lockout | Failed-login lockout configuration | Policy screenshot |
| Task Manager | Process, CPU, and memory monitoring | Original capstone report |
| Performance Monitor | CPU, memory, and disk counters | Performance screenshot |
| Event Viewer | Security, Application, and System logs | Event Viewer screenshot |
| Custom Views | Event ID filtering | Original capstone report |
| Resource Monitor | Disk, network, and memory inspection | Original capstone report |
| Network Configuration | Static IP and DNS settings | Network screenshot |
| NIC Teaming | Network adapter teaming | Network configuration documentation |
| Routing | Gateway and static route configuration | Original capstone report |
| WSUS | Role installation and update administration | WSUS screenshot |
| Windows Firewall | Inbound and outbound rules | Original capstone report |
| Printer Services | Print server and shared printer configuration | Original capstone report |
| Security Policies | Firewall, user access, and service restrictions | Original capstone report |

The original capstone report references additional screenshots for individual tasks. The six images below are the paths supplied for this GitHub README.

---

## 📸 9. Supporting Evidence

### 9.1 User Account Management

Local and domain account administration using Windows management tools and ADUC.

![User Account Management](Screenshots/User-Management.png)

**Activities Demonstrated:**

- Local user account creation.
- Domain user account management.
- Active Directory user administration.

### 9.2 Password & Account Lockout Policies

Windows account security policy configuration.

![Password and Account Lockout Policies](Screenshots/Password-and-Lockout-Policies.png)

**Activities Demonstrated:**

- Password complexity configuration.
- Password expiration settings.
- Account lockout policy configuration.

### 9.3 Performance Monitoring

Windows performance monitoring and resource analysis.

![Performance Monitoring](Screenshots/Performance-Monitoring.png)

**Activities Demonstrated:**

- CPU monitoring.
- Memory monitoring.
- System performance analysis.

### 9.4 Event Viewer Monitoring

Windows event log analysis and troubleshooting.

![Event Viewer Monitoring](Screenshots/Event-Viewer.png)

**Activities Demonstrated:**

- Security log inspection.
- Application event analysis.
- System event monitoring.

### 9.5 Network Configuration

Windows Server network interface and connectivity configuration.

![Network Configuration](Screenshots/Network-Configuration.png)

**Activities Demonstrated:**

- Network adapter configuration.
- TCP/IP settings.
- NIC Teaming concepts.
- Network redundancy fundamentals.

### 9.6 WSUS & Security Management

Windows Server update management and related security administration topics.

![WSUS and Security Management](Screenshots/WSUS-console.png)

**Activities Demonstrated:**

- WSUS administration.
- Update synchronization and approval workflows.
- Windows Server patch management concepts.

**Related Security Coverage:**

Windows Firewall rules and security policies are documented separately in the original assignment.

---

## 🧠 10. Key Learning Outcomes

- Practiced Windows Server administration.
- Created local and domain user accounts.
- Used ADUC for domain user management.
- Configured password complexity and expiration policies.
- Explored account lockout settings.
- Monitored processes using Task Manager.
- Reviewed CPU, memory, and disk performance counters.
- Analyzed Windows Application, Security, and System logs.
- Created Custom Views in Event Viewer.
- Used Resource Monitor for system analysis.
- Configured static IP and DNS settings.
- Explored NIC Teaming and network redundancy.
- Reviewed gateway and routing configuration.
- Studied WSUS installation and update approval workflows.
- Configured inbound and outbound firewall rules.
- Explored network printer sharing.
- Reviewed Windows security policies and access controls.
- Strengthened infrastructure troubleshooting and system administration skills.

---

## 🚀 11. Lab Summary

This Windows Server administration capstone covered user account management, security policies, performance monitoring, network configuration, update management, and infrastructure security.

The first assignment focused on **local and domain user accounts, password policies, account lockout, Task Manager, Performance Monitor, Event Viewer, Custom Views, and Resource Monitor**.

The second assignment covered **network configuration, NIC Teaming, routing, WSUS, Windows Firewall, printer sharing, and basic security policies**.

The documented activities and supporting evidence demonstrate foundational Windows Server administration skills developed during **Cognizant CIS Multicloud technical training**.

These exercises provide a foundation for further learning in **Windows Server administration, cloud infrastructure, system administration, IT operations, infrastructure monitoring, and DevOps engineering**.
