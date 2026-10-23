
# ☁️ Cognizant CIS Multicloud | Technical Capstone Portfolio

### Enterprise Infrastructure • Systems Administration • Networking • Virtualization • Monitoring

A structured technical repository documenting **Cognizant CIS Multicloud Engineer Trainee capstone assignments (2026)** across enterprise infrastructure technologies.

The repository consolidates hands-on laboratory exercises, technical configurations, verification results, and conceptual assignments completed during the training program.

**Focus:** Infrastructure fundamentals, technical documentation, configuration workflows, and practical exposure to enterprise IT environments.

---

## 📌 Project Overview

| Attribute | Details |
|---|---|
| Program | Cognizant CIS Multicloud |
| Role | Engineer Trainee |
| Training Period | April – September 2026 |
| Project Type | Technical Training & Capstone Assignments |
| Technical Domains | 10 |
| Documentation | Individual lab READMEs and supporting screenshots |

### Objectives

- Understand enterprise infrastructure architecture and administration.
- Practice operating system, network, and virtualization configuration.
- Explore infrastructure monitoring, automation, and storage technologies.
- Study middleware and relational database operations.
- Document implementation workflows and validate available lab results.

> **Documentation Note:** This repository represents training and capstone activities. Individual sections distinguish practical exercises, configuration results, and conceptual study. It does not represent ownership of production systems.

---

## 🧭 Technical Lab Directory

Each module links to its technical documentation, assignment objectives, workflows, and available evidence.

| # | Technical Domain | Capstone Module | Primary Technologies & Concepts |
|---|---|---|---|
| 01 | Identity & Name Resolution | [Active Directory & DNS](AD-DNS/README.md) | AD DS, DNS zones, A/AAAA/CNAME/MX records, OUs, nslookup |
| 02 | Linux Systems | [Linux Administration](Linux/README.md) | Linux CLI, file operations, permissions, package management |
| 03 | Network Infrastructure | [Networking](Networking/README.md) | TCP/IP, VLANs, routing, DHCP, DNS, wireless configuration |
| 04 | Virtualization | [VMware & Hyper-V](VMware-HyperV/README.md) | VMware ESXi, virtual machines, VM storage, templates, Hyper-V |
| 05 | Windows Infrastructure | [Windows Server](Windows-Server/README.md) | Windows Server administration, AD DS, DNS, DHCP, GPO |
| 06 | Infrastructure Automation | [PowerShell](PowerShell/README.md) | PowerShell commands, administrative scripting fundamentals |
| 07 | Storage & Data Protection | [Storage & Backup](Storage-and-Backup/README.md) | RAID, DAS/NAS/SAN, iSCSI, NetBackup, Rubrik |
| 08 | Infrastructure Observability | [Monitoring Tools](Monitoring/README.md) | SolarWinds Orion, SCOM, alerts, monitoring agents, management packs |
| 09 | Middleware & Web Infrastructure | [Middleware](Middleware/README.md) | Apache Tomcat, HTTP Server, client-server communication, IPC |
| 10 | Database Fundamentals | [Oracle DBA](Oracle-DBA/README.md) | SQL, normalization, primary/foreign keys, stored procedures |

---

## 🛠️ Technical Environment & Concepts

### Operating Systems & Identity Services

- Windows Server 2022 administration fundamentals
- Linux command-line operations and package management
- Active Directory Domain Services (AD DS)
- DNS, DHCP, organizational units, and Group Policy concepts

### Network Infrastructure

- TCP/IP and OSI networking fundamentals
- IP addressing, subnetting, VLANs, and routing
- Network device configuration exercises
- Connectivity and name-resolution verification
- Cisco Packet Tracer network simulations

### Virtualization & Infrastructure

- VMware ESXi and vCenter fundamentals
- Virtual machine provisioning and configuration
- VMware networking and storage concepts
- VM templates, migration, and backup strategies
- Microsoft Hyper-V architecture and management concepts


### Cloud Computing Fundamentals – AWS & Microsoft Azure

- **Cloud Computing Models:** IaaS, PaaS, SaaS, public, private, and hybrid cloud concepts.
- **Amazon Web Services (AWS):** EC2, S3, IAM, VPC, Security Groups, Regions, and Availability Zones.
- **Microsoft Azure:** Azure Virtual Machines, Azure Storage, Virtual Networks, and identity management fundamentals.
- **Cloud Infrastructure:** Virtual machines, cloud storage, networking, access management, and shared responsibility concepts.
- **Cloud Security:** Identity and Access Management (IAM), network security, and access control fundamentals.

### Monitoring & Operational Visibility

- SolarWinds Orion network monitoring
- Network device discovery and dashboard interpretation
- Alert configuration and monitoring results
- Microsoft System Center Operations Manager (SCOM)
- Monitoring agents and management packs
- Availability, performance, and SLA monitoring concepts

### Storage & Backup

- Direct Attached Storage (DAS)
- Network Attached Storage (NAS)
- Storage Area Networks (SAN)
- RAID levels and iSCSI
- NetBackup and Rubrik architecture
- Backup types, recovery strategies, and storage concepts

### Automation, Middleware & Databases

- PowerShell administrative scripting fundamentals
- Apache Tomcat installation and connectivity concepts
- HTTP Server configuration and web hosting fundamentals
- Client-server communication and inter-process communication
- SQL table creation and relational data modeling
- Database normalization and stored procedure fundamentals

---

## 🔬 Selected Capstone Work

The following modules provide examples of configuration-oriented assignments and documented technical results.

### 01 | Windows Server – Active Directory & DNS

**Objective:** Understand enterprise identity organization and DNS-based name resolution.

**Documented Activities:**

- DNS Server role installation and configuration
- Forward and reverse lookup zone creation
- DNS record management using A, AAAA, CNAME, and MX records
- DNS client configuration
- Name-resolution verification using `nslookup` and `ipconfig`
- Active Directory organizational unit structure

**Evidence Available:**
DNS installation, lookup zones, records, client configuration, name-resolution results, and OU structure screenshots.

[Explore AD-DNS Documentation →](AD-DNS/README.md)

---

### 02 | Network Configuration & Connectivity

**Objective:** Explore network segmentation, addressing, and communication between connected devices.

**Documented Activities:**

- Router, switch, and wireless configuration exercises
- IP addressing and network segmentation
- VLAN and inter-VLAN routing concepts
- DHCP and DNS configuration
- Network connectivity testing using ping and traceroute

**Evidence Available:**
Network topology, ping results, VLAN/SSID configuration, and DHCP/DNS configuration screenshots.

[Explore Networking Documentation →](Networking/README.md)

---

### 03 | VMware ESXi & Hyper-V

**Objective:** Understand hypervisor architecture, virtual machine management, and infrastructure virtualization.

**Documented Topics:**

- ESXi installation and network configuration
- Virtual machine provisioning and administration
- Storage repository configuration
- VM templates and deployment
- Startup/shutdown management
- Migration and backup strategies
- Hyper-V virtualization concepts

[Explore Virtualization Documentation →](VMware-HyperV/README.md)

---

### 04 | SolarWinds Orion & Microsoft SCOM

**Objective:** Explore infrastructure visibility, network monitoring, alerts, and managed system monitoring.

**Documented Activities:**

- Adding a network device in SolarWinds Orion
- Reviewing network monitoring dashboards
- Monitoring alert results
- SCOM agent deployment workflows
- Management pack configuration concepts

**Evidence Available:**
SolarWinds network device, monitoring dashboard and alert results; SCOM agent deployment and management pack screenshots.

[Explore Monitoring Documentation →](Monitoring/README.md)

---

### 05 | Apache Tomcat & Middleware

**Objective:** Understand middleware services, web application hosting, and communication between systems.

**Documented Topics:**

- Apache Tomcat server configuration concepts
- Java web application hosting fundamentals
- `JAVA_HOME` and `CATALINA_HOME`
- Server connectivity through `localhost:8080`
- Client-server communication and IPC
- Apache HTTP Server, virtual hosts, and load balancing concepts

**Evidence Available:**
Apache Tomcat welcome page demonstrating server connectivity.

[Explore Middleware Documentation →](Middleware/README.md)

---

### 06 | Relational Database Design & Stored Procedures

**Objective:** Explore structured database design and SQL-based business logic.

**Case Study 1 — Student–Course Enrollment System**

- Five related entities: Student, Course, Teacher, Department, Enrollment
- Database normalization concepts: 1NF, 2NF, 3NF
- Primary key and foreign key relationships
- SQL table creation and execution verification

**Case Study 2 — Employee Bonus Calculation**

- Employee table and sample records
- Designation-based bonus calculation
- Stored procedure fundamentals
- SQL execution results

**Evidence Available:**
SQL table creation output and employee bonus calculation results.

[Explore Oracle DBA Documentation →](Oracle-DBA/README.md)

---

## 📁 Repository Organization

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


**Documentation Approach**

Each module is organized around:

1. Assignment objective and scope
2. Technologies and concepts covered
3. Configuration or learning workflow
4. Available execution and verification evidence
5. Key technical learning outcomes

---

## 📖 Training Context

**Cognizant Technology Solutions**  
**Engineer Trainee – CIS Multicloud Practice**  
**April 2026 – September 2026**

The training program covered enterprise infrastructure technologies, including:

- Operating systems and systems administration
- Network configuration and troubleshooting fundamentals
- VMware and Hyper-V virtualization
- Storage, backup, and recovery concepts
- Infrastructure monitoring tools
- PowerShell automation fundamentals
- Middleware and database technologies
- AWS and Microsoft Azure cloud computing fundamentals

Capstone assignments were used to reinforce technical concepts through guided exercises, configuration activities, and documentation.

---

## 🔗 Engineering Learning Roadmap

This repository establishes the infrastructure foundation supporting my ongoing learning in **Cloud Engineering and DevOps Engineering**.

My next areas of technical development include:

- AWS and Azure cloud infrastructure
- Linux administration and shell scripting
- Git and GitHub workflows
- Docker and containerization
- CI/CD pipeline development
- Terraform and Infrastructure as Code
- Kubernetes fundamentals
- Cloud monitoring and observability

These technologies will be demonstrated through separate projects as practical implementations are completed.

---

## 👩‍💻 Author

**Geetha D R**  
B.E. – Electronics & Communication Engineering  
Former Engineer Trainee – Cognizant CIS Multicloud

**Current Learning Focus:** Cloud Engineering | DevOps Engineering | Infrastructure Automation

**GitHub:** [github.com/Geethadr16](https://github.com/Geethadr16)

---

*Technical capstone documentation | Cognizant CIS Multicloud Training – 2026*
