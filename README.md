
# ☁️ Cognizant CIS Multicloud | Technical Capstone Portfolio

### Enterprise Infrastructure • Systems Administration • Networking • Virtualization • Monitoring

A technical portfolio documenting **10 infrastructure training modules** completed during the **Cognizant CIS Multicloud Engineer Trainee program (2026)**.

This repository brings together guided technical assignments, configuration workflows, administration exercises, supporting screenshots, and conceptual studies across enterprise IT infrastructure technologies.

The portfolio focuses on **infrastructure administration, technical problem-solving, system configuration, troubleshooting fundamentals, and structured technical documentation**.

> **Portfolio Scope:** This repository documents training and capstone assignments, not production infrastructure ownership. Practical activities, screenshot-supported results, and conceptual topics are distinguished in the individual modules.

---

## 📌 1. Portfolio Overview

| Attribute | Details |
|---|---|
| Organization | Cognizant Technology Solutions |
| Program | CIS Multicloud |
| Role | Engineer Trainee |
| Training Period | April – September 2026 |
| Project Type | Infrastructure Training & Technical Capstone |
| Technical Modules | 10 |
| Repository Documentation | 10 Module READMEs + 1 Main README |
| Primary Focus | Windows Server, Linux, Networking, Virtualization, Monitoring |
| Career Direction | Cloud Engineering & DevOps Engineering |

### Objectives

- Understand enterprise infrastructure architecture and administration.
- Practice operating system configuration and user administration.
- Explore network configuration, connectivity, and troubleshooting.
- Understand hypervisor deployment and virtual machine management.
- Study storage, SAN, and backup technologies.
- Explore infrastructure monitoring and alert management.
- Apply foundational PowerShell administration commands.
- Understand middleware and relational database operations.
- Document technical workflows and available verification results.

---

## 🧭 2. Technical Lab Directory

Each module contains assignment objectives, technical explanations, implementation or learning workflows, and available supporting evidence.

| # | Technical Domain | Module | Primary Technologies & Concepts |
|---|---|---|---|
| 01 | Identity & Name Resolution | [🔐 Active Directory & DNS](AD-DNS/README.md) | DNS Server, forward/reverse zones, A/AAAA/CNAME/MX records, AD OUs, `nslookup` |
| 02 | Linux Systems | [🐧 Linux Administration](Linux/README.md) | Linux CLI, file and directory management, permissions, package management |
| 03 | Network Infrastructure | [🌐 Networking](Networking/README.md) | TCP/IP, VLANs, routing, DHCP, DNS, wireless configuration, device simulation |
| 04 | Virtualization | [🖥️ VMware & Hyper-V](VMware-HyperV/README.md) | VMware ESXi, datastores, VMs, templates, snapshots, migration and Hyper-V concepts |
| 05 | Windows Infrastructure | [⚙️ Windows Server](Windows-Server/README.md) | User administration, password policies, monitoring, NIC Teaming, WSUS, firewall |
| 06 | Infrastructure Automation | [⚡ PowerShell](PowerShell/README.md) | Cmdlets, pipelines, process/service monitoring, aliases, CSV and JSON |
| 07 | Storage & Data Protection | [💾 Storage & Backup](Storage-and-Backup/README.md) | RAID, multipathing, SAN, Brocade/Cisco switches, zoning, NetBackup, Rubrik |
| 08 | Infrastructure Monitoring | [📊 Monitoring Tools](Monitoring/README.md) | SolarWinds Orion, SCOM, SNMP, alerts, agents, management packs |
| 09 | Middleware & Web Infrastructure | [🔧 Middleware](Middleware/README.md) | Apache Tomcat, client-server communication, IPC, Apache HTTP Server |
| 10 | Database Fundamentals | [🗄️ Oracle DBA](Oracle-DBA/README.md) | SQL, relational modeling, normalization, primary/foreign keys, stored procedures |

---

## 🛠️ 3. Technical Environment & Skills

### Operating Systems & Identity Services

- Windows Server 2022 administration fundamentals.
- Linux command-line operations and package management.
- Local and domain user administration.
- Active Directory Domain Services (AD DS).
- DNS, DHCP, Organizational Units, and Group Policy.
- Password and account lockout policies.
- Windows Event Viewer and resource monitoring.

### Network Infrastructure

- TCP/IP and OSI networking fundamentals.
- IP addressing and subnetting.
- VLANs and inter-VLAN routing.
- Static routing and default gateway concepts.
- DHCP and DNS configuration.
- Router, switch, and wireless configuration exercises.
- Connectivity verification using ping and traceroute.
- Network topology and device simulation.

### Virtualization & Infrastructure

- VMware ESXi installation and initial configuration.
- VMware Host Client administration.
- Virtual machine creation and lifecycle management.
- Management networking and datastore configuration.
- Virtual machine templates and deployment workflows.
- Snapshot management and backup concepts.
- VMware vMotion and migration fundamentals.
- Microsoft Hyper-V architecture and management concepts.

### Infrastructure Monitoring

- SolarWinds Orion monitoring.
- Network device discovery and monitoring dashboards.
- Network performance and traffic monitoring concepts.
- Alert configuration and monitoring results.
- Microsoft System Center Operations Manager (SCOM).
- Monitoring agents and management packs.
- Event analysis, reporting, and notification concepts.

### Storage & Backup

- Direct Attached Storage (DAS).
- Network Attached Storage (NAS).
- Storage Area Networks (SAN).
- RAID 0, RAID 1, and RAID 5.
- Storage multipathing fundamentals.
- Block, file, and object storage.
- Brocade and Cisco SAN switch management.
- WWN-based zoning concepts.
- NetBackup and Rubrik architecture.
- Full, incremental, differential, and synthetic backups.
- NDMP and recovery concepts.

### Automation, Middleware & Databases

- PowerShell administrative cmdlets.
- Process and service management.
- PowerShell pipelines and aliases.
- CSV export and JSON conversion concepts.
- Apache Tomcat server installation and connectivity.
- Client-server communication and IPC.
- Apache HTTP Server and virtual hosting concepts.
- SQL table creation and relational modeling.
- Database normalization.
- Stored procedure fundamentals.

### Cloud Computing Fundamentals

The broader training program also introduced AWS and Microsoft Azure fundamentals.

**Amazon Web Services**

- Amazon EC2.
- Amazon S3.
- AWS IAM.
- Amazon VPC.
- Security Groups.
- Regions and Availability Zones.

**Microsoft Azure**

- Azure Virtual Machines.
- Azure Storage.
- Virtual networking.
- Cloud identity and access management fundamentals.

**Cloud Architecture Concepts**

- IaaS, PaaS, and SaaS.
- Public, private, and hybrid cloud.
- Cloud networking and storage.
- Shared responsibility and cloud security fundamentals.

These cloud topics represent foundational training exposure rather than separately demonstrated cloud deployment projects in this repository.

---

## 🔬 4. Selected Technical Capstone Work

The following assignments highlight representative technical activities and supporting evidence.

### 4.1 Active Directory & DNS Administration

**Objective:** Understand enterprise identity organization and DNS-based name resolution.

**Documented Activities:**

- DNS Server role installation and configuration.
- Forward and reverse lookup zone creation.
- DNS record management using A, AAAA, CNAME, and MX records.
- DNS client configuration.
- Name-resolution verification using `nslookup` and `ipconfig`.
- Active Directory Organizational Unit structure.
- Review of DNS resolution across Windows environments.

**Supporting Evidence:**

DNS installation, lookup zones, DNS records, client configuration, name-resolution verification, and OU screenshots.

[Explore AD-DNS Documentation →](AD-DNS/README.md)

### 4.2 Linux Administration

**Objective:** Understand Linux administration using command-line tools.

**Documented Activities:**

- Basic Linux commands and system navigation.
- File and directory creation.
- Copying, moving, and deleting files.
- File permissions and ownership.
- Absolute and relative paths.
- Package management operations.
- Package installation, update, and removal workflows.

**Supporting Evidence:**

Linux command execution, directory management, and package management screenshots.

[Explore Linux Documentation →](Linux/README.md)

### 4.3 Network Configuration & Connectivity

**Objective:** Understand network segmentation, addressing, connectivity, and device configuration.

**Documented Activities:**

- Router, switch, and wireless configuration exercises.
- IP addressing and subnetting.
- VLAN configuration and inter-VLAN routing concepts.
- Wireless security and SSID configuration.
- DHCP and DNS configuration.
- LAN, WAN, WLAN, and SOHO network concepts.
- Network device simulation and configuration.
- Connectivity testing using ping and traceroute.

**Supporting Evidence:**

Network topology, ping results, VLAN/SSID settings, and DHCP/DNS configuration screenshots.

[Explore Networking Documentation →](Networking/README.md)

### 4.4 VMware ESXi & Hyper-V Virtualization

**Objective:** Understand hypervisor deployment, virtual machine administration, and virtualization infrastructure.

**Documented Activities:**

- VMware ESXi installation.
- Management network and remote administration.
- User and role administration.
- Datastore configuration.
- Virtual machine creation and power operations.
- VM template and deployment workflows.
- Startup and shutdown configuration.
- Snapshot management.
- Migration and backup strategy concepts.
- Hyper-V virtualization fundamentals.

**Supporting Evidence:**

ESXi installation, network configuration, datastore management, VM administration, template creation, and snapshot management screenshots.

**Technical Scope:** Migration and Hyper-V concepts are distinguished from VMware configuration activities.

[Explore VMware & Hyper-V Documentation →](VMware-HyperV/README.md)

### 4.5 Windows Server Administration

**Objective:** Understand Windows Server user management, monitoring, networking, and security administration.

**Documented Activities:**

- Local and domain user account creation.
- Password complexity and expiration policies.
- Account lockout configuration.
- Task Manager and Performance Monitor.
- Event Viewer and Custom Event Views.
- Resource Monitor.
- Static IP and DNS configuration.
- NIC Teaming and routing.
- WSUS role and update administration.
- Windows Firewall rules.
- Network printer services.
- Security policies and user access controls.

**Supporting Evidence:**

User management, password policies, performance monitoring, Event Viewer, network configuration, and WSUS screenshots.

[Explore Windows Server Documentation →](Windows-Server/README.md)

### 4.6 PowerShell Administration

**Objective:** Understand command-line administration and basic automation using PowerShell.

**Documented Activities:**

- Process inspection using `Get-Process`.
- Service inspection using `Get-Service`.
- Filtering results with `Where-Object`.
- Using PowerShell pipelines.
- Working with aliases.
- Exporting administrative information to CSV.
- Reviewing JSON data conversion.
- File and directory administration concepts.

**Supporting Evidence:**

Process/service commands, pipeline filtering, aliases, and CSV export screenshots.

[Explore PowerShell Documentation →](PowerShell/README.md)

### 4.7 Storage & Backup Technologies

**Objective:** Understand enterprise storage infrastructure and data protection.

**Documented Topics:**

- RAID 0, RAID 1, and RAID 5.
- Storage multipathing.
- Block, file, and object storage.
- SAN switch architecture.
- Brocade and Cisco switch administration workflows.
- WWN and port zoning.
- NetBackup and Rubrik architecture.
- VM and physical server backup planning.
- Full, incremental, differential, and synthetic backups.
- NDMP-based NAS backup concepts.

**Supporting Evidence:**

RAID concepts, Brocade switch configuration, Cisco SAN configuration, and zoning screenshots.

[Explore Storage & Backup Documentation →](Storage-and-Backup/README.md)

### 4.8 SolarWinds Orion & Microsoft SCOM

**Objective:** Understand infrastructure monitoring, network visibility, and operational alerting.

**Documented Activities:**

- Adding a network device in SolarWinds Orion.
- Reviewing monitoring dashboards.
- Exploring SNMP-based monitoring.
- Monitoring alert results.
- Reviewing network traffic analysis concepts.
- SCOM agent deployment workflows.
- Management pack configuration.
- Monitoring notifications and reporting concepts.

**Supporting Evidence:**

SolarWinds network device, monitoring dashboard, alert results, SCOM agent deployment, and management pack screenshots.

[Explore Monitoring Documentation →](Monitoring/README.md)

### 4.9 Apache Tomcat & Middleware

**Objective:** Understand middleware services and communication between applications and systems.

**Documented Topics:**

- Apache Tomcat installation and configuration.
- Java runtime environment concepts.
- Tomcat server connectivity.
- `JAVA_HOME` and `CATALINA_HOME`.
- Accessing Tomcat through `localhost:8080`.
- Client-server communication.
- Inter-process communication.
- Apache HTTP Server concepts.
- Virtual hosting, routing, and load balancing fundamentals.

**Supporting Evidence:**

Apache Tomcat welcome page demonstrating server connectivity.

[Explore Middleware Documentation →](Middleware/README.md)

### 4.10 Relational Database Design & Stored Procedures

**Objective:** Understand relational database design and SQL-based business logic.

**Case Study 1 — Student–Course Enrollment**

- Five related entities: Student, Course, Teacher, Department, and Enrollment.
- Primary and foreign key relationships.
- Database normalization: 1NF, 2NF, and 3NF.
- SQL table creation and relational structure.

**Case Study 2 — Employee Bonus Calculation**

- Employee data and sample records.
- Designation-based bonus calculation.
- Stored procedure logic.
- SQL execution results.

**Supporting Evidence:**

SQL table creation and stored procedure execution screenshots.

[Explore Oracle DBA Documentation →](Oracle-DBA/README.md)

---

## 🏗️ 5. Enterprise Infrastructure Architecture — Conceptual View

The 10 modules represent technologies commonly used across different layers of enterprise infrastructure.

```text
                    Enterprise IT Infrastructure
                                |
            +-------------------+-------------------+
            |                   |                   |
            v                   v                   v
       Operating Systems   Network Services    Virtualization
       Windows / Linux     DNS / DHCP / VLAN   VMware / Hyper-V
            |                   |                   |
            +-------------------+-------------------+
                                |
                                v
                       Infrastructure
                         Operations
                                |
               +----------------+----------------+
               |                |                |
               v                v                v
            Monitoring       Automation      Data Protection
          SolarWinds/SCOM    PowerShell      Storage & Backup
                                |
                                v
                         Applications &
                            Databases
                         Tomcat / SQL
```

**Architecture Note:** This diagram illustrates relationships between training domains. It does not represent a single integrated production environment deployed during the capstone.

---

## 📁 6. Repository Organization

```text
cognizant-cis-multicloud-capstone/
│
├── AD-DNS/
│   ├── README.md
│   └── Screenshots/
│
├── Linux/
│   ├── README.md
│   └── Screenshots/
│
├── Networking/
│   ├── README.md
│   └── Screenshots/
│
├── VMware-HyperV/
│   ├── README.md
│   └── Screenshots/
│
├── Windows-Server/
│   ├── README.md
│   └── Screenshots/
│
├── PowerShell/
│   ├── README.md
│   └── Screenshots/
│
├── Storage-and-Backup/
│   ├── README.md
│   └── Screenshots/
│
├── Monitoring/
│   ├── README.md
│   └── Screenshots/
│
├── Middleware/
│   ├── README.md
│   └── Screenshots/
│
├── Oracle-DBA/
│   ├── README.md
│   └── Screenshots/
│
└── README.md
```

### Documentation Approach

Each technical module is organized around:

1. Assignment objectives and technical scope.
2. Lab environment and technologies.
3. Configuration activities and learning workflows.
4. Technical explanations and concepts.
5. Available verification results and screenshots.
6. Key learning outcomes.
7. Lab summary.

Screenshots are used to support documented activities where available. Conceptual topics are identified separately rather than presented as independently verified implementations.

---

## 📚 7. Training Context

**Cognizant Technology Solutions**  
**Engineer Trainee — CIS Multicloud**  
**April 2026 – September 2026**

The training program introduced enterprise infrastructure technologies through guided technical modules, administration exercises, and capstone assignments.

**Core Training Areas:**

- Windows Server and Linux administration.
- Networking and troubleshooting fundamentals.
- VMware and Hyper-V virtualization.
- Storage, backup, and recovery.
- Infrastructure monitoring.
- PowerShell administration.
- Middleware technologies.
- Database fundamentals.
- AWS and Microsoft Azure cloud fundamentals.

The capstone assignments reinforced selected technical concepts through configuration exercises, simulated environments, documentation, and available verification evidence.

---

## 🚀 8. Cloud & DevOps Engineering Roadmap

This repository establishes my foundational understanding of enterprise infrastructure technologies.

My next focus is developing a **separate Cloud & DevOps engineering project portfolio** demonstrating practical implementation, infrastructure automation, and deployment workflows.

| Technology | Planned Learning & Project Focus |
|---|---|
| Linux | System administration and shell scripting |
| Git & GitHub | Version control, branching, collaboration, repository management |
| AWS | EC2, IAM, VPC, S3, cloud infrastructure deployment |
| Docker | Application containerization |
| GitHub Actions | CI/CD workflow development |
| Terraform | Infrastructure as Code |
| Kubernetes | Container orchestration fundamentals |
| Monitoring | Infrastructure and application observability |

**Roadmap Status:** These are planned learning areas and future projects, not completed implementations documented in this repository.

As practical projects are completed, they will be maintained in separate repositories with architecture diagrams, implementation steps, configuration files, and verification results.

---

## 👩‍💻 9. About the Author

**Geetha D R**  
B.E. — Electronics & Communication Engineering  
Former Engineer Trainee — Cognizant CIS Multicloud

My technical interests include **Cloud Engineering, DevOps Engineering, Linux administration, infrastructure automation, and enterprise systems**.

This repository reflects my infrastructure training foundation and my approach to technical learning through configuration exercises, documentation, and supporting evidence.

**GitHub:** [github.com/Geethadr16](https://github.com/Geethadr16)

---

*Technical Capstone Portfolio | Cognizant CIS Multicloud Training | 2026*
