
# 💾 Storage & Backup Administration | Enterprise Infrastructure Lab

## 📌 1. Overview

This module documents enterprise storage and backup administration assignments completed during the **Cognizant CIS Multicloud technical capstone training program**.

The training covered RAID configurations, storage architectures, multipathing, Storage Area Networks (SAN), Brocade and Cisco SAN switch administration, Fibre Channel zoning, enterprise backup platforms, and data protection strategies.

The assignments combined infrastructure concepts, documented switch-configuration workflows, storage architecture analysis, and backup planning.

**Assignments Covered:**

1. **RAID & Storage Fundamentals:** RAID levels, multipathing, and block, file, and object storage.
2. **Brocade & Cisco SAN Administration:** SAN architecture, switch management, host integration, and zoning.
3. **NetBackup & Rubrik:** Enterprise backup architecture, backup planning, backup types, and disaster recovery fundamentals.

## 🛠️ 2. Technologies & Concepts Covered

| Technology / Concept | Purpose | Training Coverage |
|---|---|---|
| RAID | Disk-level performance and redundancy | RAID 0, 1, and 5 |
| Multipathing | Redundant server-to-storage connectivity | Windows MPIO and vendor-specific solutions |
| Block Storage | Block-level data access | Databases and virtual machines |
| File Storage | File-based data access | NAS and shared directories |
| Object Storage | Object-based data storage | Cloud storage and archives |
| SAN | Dedicated storage networking | Architecture and connectivity |
| Fibre Channel | High-speed storage communication | SAN fundamentals |
| Brocade SAN | Enterprise Fibre Channel switching | Switch management and zoning workflows |
| Cisco SAN | Enterprise storage networking | CLI management concepts |
| WWN & Port-Based Zoning | Controlling SAN device communication | Host integration |
| NetBackup | Enterprise backup and recovery | Architecture and backup planning |
| Rubrik | Policy-based data protection | Platform concepts |
| NDMP | Network storage backup protocol | NAS backup fundamentals |

## 🎯 3. Technical Objectives

- Understand enterprise storage architectures and their use cases.
- Compare RAID levels and their performance and redundancy characteristics.
- Explore native and vendor-specific multipathing.
- Differentiate block, file, and object storage.
- Understand SAN architecture and Fibre Channel connectivity.
- Study Brocade and Cisco SAN switch management.
- Review management IP configuration, authentication, and port monitoring.
- Understand WWN-based and port-based zoning.
- Explore SAN host-to-storage access control.
- Understand NetBackup and Rubrik architectures.
- Review backup planning for virtual machines and physical servers.
- Compare full, incremental, differential, and synthetic backups.
- Understand NDMP-based NAS backup.
- Explore data protection, disaster recovery, and business continuity concepts.

---

## 🗂️ 4. Assignment 1 — RAID Concepts & Storage Fundamentals

### 4.1 Understanding RAID

**Objective:** Understand how RAID configurations influence storage performance, availability, and fault tolerance.

RAID stands for **Redundant Array of Independent Disks**.

RAID combines multiple physical disks into a logical storage arrangement to achieve specific performance or redundancy goals.

The assignment covered three RAID levels.

| RAID Level | Configuration | Main Advantage | Limitation |
|---|---|---|---|
| RAID 0 | Data striping | Improved throughput | No redundancy |
| RAID 1 | Data mirroring | Disk redundancy | Additional storage capacity required |
| RAID 5 | Striping with distributed parity | Capacity efficiency with single-disk fault tolerance | Parity overhead and rebuild considerations |

### 4.2 RAID 0 — Striping

RAID 0 distributes data across multiple disks.

**Conceptual Structure:**

```text
          RAID 0 — Striping

             Data Blocks
                  |
           +------+------+
           |             |
           v             v
         Disk 1        Disk 2
         ------        ------
         Block A       Block B
         Block C       Block D
```

**Characteristics:**

- Distributes data across disks.
- Can improve read and write throughput.
- Does not provide fault tolerance.
- Failure of one member disk can make the entire array unusable.

**Primary Use Case:** Performance-focused workloads where data protection is handled separately.

### 4.3 RAID 1 — Mirroring

RAID 1 maintains mirrored copies of data across disks.

**Conceptual Structure:**

```text
          RAID 1 — Mirroring

             Data Blocks
                  |
           +------+------+
           |             |
           v             v
         Disk 1        Disk 2
         ------        ------
         Block A       Block A
         Block B       Block B
```

**Characteristics:**

- Maintains redundant copies of data.
- Can tolerate a disk failure in a two-disk mirror.
- Provides availability benefits.
- Requires additional disk capacity.

**Primary Use Case:** Storage requiring disk-level redundancy.

### 4.4 RAID 5 — Distributed Parity

RAID 5 distributes data and parity information across at least three disks.

**Conceptual Structure:**

```text
         RAID 5 — Distributed Parity

         Disk 1    Disk 2    Disk 3
         ------    ------    ------
         Data A    Data B    Parity
         Data C    Parity    Data D
         Parity    Data E    Data F
```

**Characteristics:**

- Requires at least three disks.
- Uses distributed parity.
- Can tolerate one member-disk failure.
- Balances usable capacity and redundancy.
- Write operations may incur parity overhead.

**Primary Use Case:** General-purpose storage requiring capacity efficiency and disk fault tolerance.

### 4.5 Understanding Multipathing

Multipathing establishes multiple paths between a server and a storage device.

Its primary purpose is to improve storage connectivity resilience and, depending on the implementation, distribute I/O traffic.

**Conceptual Architecture:**

```text
                  Server
                    |
             Multipath Layer
                /       \
               v         v
           Path 1       Path 2
               \         /
                v       v
               Storage
                 Array
```

If one supported storage path fails, another available path can maintain connectivity.

### 4.6 Types of Multipathing

The assignment covered two approaches.

| Type | Description | Example |
|---|---|---|
| Native Multipathing | Multipath functionality provided by the operating system | Windows MPIO |
| Vendor-Specific Multipathing | Multipath solutions provided or optimized by storage vendors | Vendor storage path-management software |

**Windows MPIO**

Multipath I/O (MPIO) allows Windows systems to manage multiple storage paths when supported by the storage hardware and configuration.

**Vendor-Specific Multipathing**

Vendor-provided solutions may offer additional path management, failover, and optimization capabilities.

### 4.7 Benefits of Multipathing

- **High Availability:** Alternate paths can maintain storage connectivity.
- **Fault Tolerance:** Reduces dependence on a single connection.
- **Load Balancing:** Supported configurations can distribute I/O across paths.
- **Performance:** Multiple active paths may improve throughput under suitable workloads.

Multipathing protects access paths; it does not replace backup or guarantee protection against data corruption.

### 4.8 Block Storage

Block storage presents data as addressable blocks that a host operating system can manage.

**Common Use Cases:**

- Oracle and SQL Server databases.
- Virtual machine disks.
- High-performance applications.
- Enterprise storage volumes.

### 4.9 File Storage

File storage organizes data into files and directories.

**Common Use Cases:**

- Shared folders.
- Network Attached Storage (NAS).
- User home directories.
- Departmental file repositories.

### 4.10 Object Storage

Object storage manages data as objects containing content, metadata, and identifiers.

**Common Use Cases:**

- Amazon S3.
- Azure Blob Storage.
- Backup repositories.
- Archival storage.
- Large-scale unstructured data.

### 4.11 Storage Architecture Comparison

| Storage Type | Access Model | Typical Use Case |
|---|---|---|
| Block | Block devices and volumes | Databases and virtual machines |
| File | File and directory paths | Shared files and NAS |
| Object | Object APIs and identifiers | Cloud storage and archives |

### 4.12 Organizational Benefits

Enterprise storage technologies support:

- Data availability.
- Storage performance.
- Scalable capacity planning.
- Fault tolerance.
- Infrastructure resilience.
- Business continuity.

**Important:** RAID and multipathing address particular hardware or connectivity failures. They do not replace independent backups or a disaster recovery strategy.

### Technical Outcome

Studied RAID 0, RAID 1, and RAID 5; reviewed native and vendor-specific multipathing; and compared block, file, and object storage architectures.

---

## 🌐 5. Assignment 2 — Brocade & Cisco SAN Administration

### 5.1 Understanding Storage Area Networks

**Objective:** Understand SAN switch architecture, management, and host-to-storage connectivity.

A **Storage Area Network (SAN)** provides specialized connectivity between servers and shared storage systems.

Enterprise Fibre Channel SANs commonly use dedicated switching infrastructure to support block-level storage access.

**Conceptual SAN Architecture:**

```text
             Application Servers
                  /       \
                 v         v
             SAN Fabric / Switches
                  \       /
                   v     v
                Storage Array
                     |
                 Disk Volumes
```

### 5.2 SAN Switch Fundamentals

A SAN switch connects hosts and storage devices within a storage fabric.

The assignment covered:

- Fibre Channel connectivity.
- Brocade SAN switches.
- Cisco SAN switches.
- SAN port management.
- Switch administration.
- Host-to-storage communication.
- Storage access control.

### 5.3 Brocade SAN Switches

Brocade SAN switches are used in enterprise Fibre Channel environments.

**Concepts Covered:**

- Switch management.
- Fibre Channel ports.
- Administrative access.
- Zoning.
- Connectivity monitoring.
- Storage fabric configuration.

### 5.4 Cisco SAN Switches

Cisco provides enterprise SAN switching solutions, including the MDS family.

**Concepts Covered:**

- CLI-based administration.
- Management interface configuration.
- Switch identification.
- Configuration persistence.
- SAN connectivity.

### 5.5 SAN Switch Management Methods

The original assignment covered two administrative methods.

| Method | Description |
|---|---|
| CLI | Command-line configuration and monitoring |
| GUI | Graphical administration through supported management interfaces or tools |

**Common Management Activities:**

- Configure management IP addresses.
- Authenticate administrative users.
- Review switch identification.
- Monitor port status.
- Inspect connectivity.
- Save configuration changes.

### 5.6 Brocade SAN Switch Configuration Workflow

The capstone documented the following administrative sequence.

**Step 1 — Access the Switch**

Connect through an available management interface, such as a console session or SSH, and authenticate with authorized credentials.

**Step 2 — Configure Management IP**

Assign management network settings to support remote administration.

**Step 3 — Configure Switch Name**

Set a recognizable switch name for easier identification.

**Step 4 — Review or Enable Switch Operation**

Inspect operational state and applicable switch or port settings.

**Step 5 — Save Configuration**

Persist supported configuration changes.

**Purpose:**

These steps establish a basic workflow for managing a Brocade SAN switch.

The source report describes the configuration sequence but does not establish a verified production switch deployment.

### 5.7 Cisco SAN Switch Configuration Workflow

The assignment also documented Cisco SAN administration.

**Step 1 — Enter Configuration Mode**

Access the supported configuration environment.

**Step 2 — Configure Management Interface**

Assign appropriate management network settings.

**Step 3 — Configure Switch Name**

Set the switch hostname.

**Step 4 — Save Configuration**

Preserve the configuration for future operation.

**Purpose:**

These activities introduce common Cisco SAN switch administration concepts.

### 5.8 Understanding SAN Zoning

**Objective:** Understand how zoning controls communication between devices in a Fibre Channel SAN.

Zoning groups selected initiators and targets into permitted communication sets.

It is commonly used to manage which hosts can communicate with particular storage ports.

### 5.9 Types of SAN Zoning

| Zoning Type | Description |
|---|---|
| WWN-Based Zoning | Identifies zone members using World Wide Names |
| Port-Based Zoning | Uses physical switch ports as zone members |

**WWN-Based Zoning**

Uses device identities such as World Wide Port Names (WWPNs).

**Port-Based Zoning**

Associates zone membership with specified switch ports.

### 5.10 Host-to-Storage Zoning Architecture

**Conceptual Example:**

```text
                SAN Switch
                    |
              Active Zone
               /       \
              v         v
          Host HBA    Storage Port
              |           |
              +-----------+
              Permitted Access
```

Devices that are not included in a permitted zone are restricted according to the fabric's zoning configuration.

Zoning controls fabric communication but is not a substitute for storage LUN masking or host-level access controls.

### 5.11 Brocade Zoning Configuration Workflow

The original capstone covered five configuration stages.

**Step 1 — Create an Alias**

Define a readable alias representing a host or storage port.

**Step 2 — Create a Zone**

Associate the required host and storage members.

**Step 3 — Create a Zone Configuration**

Organize the relevant zones into a zone configuration.

**Step 4 — Enable the Configuration**

Activate the intended zone configuration.

**Step 5 — Save the Configuration**

Preserve the changes.

**Conceptual Workflow:**

```text
          Identify Host & Storage
                    |
                    v
              Create Aliases
                    |
                    v
                Create Zone
                    |
                    v
          Create Zone Configuration
                    |
                    v
           Enable Configuration
                    |
                    v
           Save Configuration
```

This represents the documented workflow rather than a verified execution transcript.

### 5.12 Benefits of SAN Zoning

- Controls communication between SAN devices.
- Limits unnecessary host-to-target visibility.
- Supports organized storage access.
- Helps isolate workloads.
- Reduces unintended fabric interactions.
- Supports SAN security administration.

### Technical Outcome

Studied Brocade and Cisco SAN administration, switch management workflows, Fibre Channel connectivity, WWN-based and port-based zoning, and host-to-storage access control.

---

## 🛡️ 6. Assignment 3 — NetBackup & Rubrik Administration

### 6.1 Understanding Enterprise Backup

**Objective:** Understand enterprise backup architectures and the processes used to protect and recover data.

Backup systems create recoverable copies of information to support restoration after data loss, corruption, or infrastructure failure.

The assignment covered two enterprise backup platforms:

- NetBackup.
- Rubrik.

### 6.2 NetBackup Overview

NetBackup is an enterprise backup and recovery platform.

The original assignment describes its architecture using three major components.

| Component | Responsibility |
|---|---|
| Master Server | Coordinates backup administration and policies |
| Media Server | Manages backup data transfer and storage interaction |
| Client | Represents a system or workload being protected |

The terms above reflect the architecture used in the training report. Newer NetBackup documentation may use updated component terminology.

### 6.3 NetBackup Architecture

**Conceptual Workflow:**

```text
              Master Server
                    |
             Backup Policies
                    |
             +------+------+
             |             |
             v             v
         Media Server   Client Systems
             |
             v
        Backup Storage
```

The architecture introduces centralized backup management, protected clients, and storage handling.

### 6.4 Rubrik Overview

Rubrik is an enterprise data protection platform that supports policy-based backup management and recovery.

**Features Studied:**

- Policy-based backup scheduling.
- Automated backup operations.
- Cloud integration.
- Backup and recovery management.
- Data protection workflows.

### 6.5 NetBackup vs. Rubrik — Training Comparison

| Area | NetBackup | Rubrik |
|---|---|---|
| Primary Purpose | Enterprise backup and recovery | Enterprise data protection and recovery |
| Training Focus | Master server, media server, and clients | Policy-based backup and automation |
| Management Concepts | Backup administration and scheduling | Policy-driven administration |
| Workload Protection | Enterprise systems and workloads | Enterprise systems and workloads |
| Recovery | Backup-based data restoration | Managed recovery operations |

The comparison summarizes the training topics and does not represent a product benchmark.

### 6.6 Backup Planning for Virtual Machines

The assignment covered backup planning for virtualized workloads.

**Conceptual Activities:**

1. Identify virtual machines requiring protection.
2. Select an appropriate backup method.
3. Define a backup schedule.
4. Choose a storage destination.
5. Configure retention requirements.
6. Plan recovery and verification procedures.

### 6.7 Backup Planning for Physical Servers

The training also covered physical server backup requirements.

**Conceptual Activities:**

- Identify critical servers.
- Select protected data and applications.
- Define backup schedules.
- Assign backup storage.
- Review recovery requirements.
- Plan periodic restore testing.

These are documented planning concepts rather than proof of completed backup jobs or restore tests.

### 6.8 Understanding Backup Types

The original assignment covered full, incremental, differential, and synthetic backups.

| Backup Type | Description | Main Consideration |
|---|---|---|
| Full | Copies all selected data | Larger backup workload |
| Incremental | Copies changes since the relevant preceding backup | May require multiple restore points |
| Differential | Copies changes since the last full backup | Differential size may grow over time |
| Synthetic Full | Constructs a full backup using existing backup data | Reduces the need to reread all source data |

### 6.9 Full Backup

A full backup copies all selected data.

**Characteristics:**

- Provides a complete backup baseline.
- May require significant time and storage.
- Can simplify restoration when a valid full backup is available.

### 6.10 Incremental Backup

An incremental backup captures data changed since the preceding relevant backup.

**Characteristics:**

- Usually reduces the amount of data copied.
- Can shorten backup windows.
- Recovery may depend on a full backup and subsequent incremental backups.

### 6.11 Differential Backup

A differential backup captures changes since the last full backup.

**Characteristics:**

- Each differential includes changes accumulated since the full backup.
- Differential backup size can increase over time.
- A typical restore requires the full backup and the selected differential.

### 6.12 Synthetic Full Backup

A synthetic full backup constructs a new full backup from existing backup data.

**Characteristics:**

- Uses previously backed-up data.
- Can reduce source-system read activity.
- Depends on backup platform capabilities and stored backup data.

### 6.13 NDMP Backup

NDMP stands for **Network Data Management Protocol**.

It supports backup and recovery operations for compatible network-attached storage systems.

**Concepts Covered:**

- NAS backup.
- Backup software integration.
- Storage-based data transfer.
- Centralized backup administration.

**Conceptual Architecture:**

```text
              Backup Platform
                     |
              NDMP Coordination
                     |
                     v
                 NAS System
                     |
                     v
              Backup Destination
```

Depending on the implementation, NDMP can allow backup data to move without passing through the application server.

### 6.14 Backup & Recovery Planning

The training introduced backup planning concepts relevant to enterprise operations.

**Key Considerations:**

- Backup frequency.
- Retention requirements.
- Storage capacity.
- Workload criticality.
- Recovery procedures.
- Data protection requirements.

Two useful disaster recovery metrics are:

| Metric | Meaning |
|---|---|
| RPO (Recovery Point Objective) | Maximum acceptable data-loss period |
| RTO (Recovery Time Objective) | Target time to restore service |

RPO and RTO are included here as related disaster recovery concepts; the source assignment does not document measured RPO or RTO values.

### 6.15 Purpose of Enterprise Backup Systems

- Protect critical business data.
- Support recovery after accidental deletion or corruption.
- Enable restoration after infrastructure failures.
- Support disaster recovery planning.
- Contribute to business continuity.
- Help meet applicable retention and compliance requirements.

### Technical Outcome

Studied NetBackup and Rubrik architectures, backup planning for virtual and physical servers, backup methods, NDMP, and enterprise recovery concepts.

---

## 📊 7. Storage & Data Protection Comparison

| Technology | Primary Purpose | Protects Against / Supports |
|---|---|---|
| RAID | Disk-level performance or redundancy | Certain disk failures, depending on RAID level |
| Multipathing | Redundant storage connectivity | Supported path failures |
| SAN Zoning | Control of fabric communication | Unintended host-to-target visibility |
| Backup | Recoverable copies of data | Data loss and recovery scenarios |
| Disaster Recovery | Restoration of critical services | Major service disruptions |

**Key Distinction:**

RAID, multipathing, zoning, and backups serve different purposes. A resilient enterprise storage design may use several of these technologies together.

---

## ✅ 8. Assignment Review & Technical Results

| Assignment | Technical Coverage | Evidence / Learning |
|---|---|---|
| RAID Fundamentals | RAID 0, 1, and 5 | RAID architecture documentation |
| Multipathing | Native and vendor-specific multipathing | Technical study |
| Storage Types | Block, file, and object storage | Architecture comparison |
| Brocade SAN | Switch management workflow | Configuration documentation |
| Cisco SAN | CLI management workflow | Configuration documentation |
| SAN Zoning | WWN and port-based zoning | Zoning documentation |
| NetBackup | Backup architecture | Conceptual understanding |
| Rubrik | Policy-based backup and recovery | Conceptual understanding |
| Backup Configuration | VM and physical server planning | Planning concepts |
| Backup Types | Full, incremental, differential, synthetic, NDMP | Technical study |

The source report primarily documents architecture, administrative workflows, and theoretical concepts. It does not establish successful production SAN changes or completed backup and restore jobs.

---

## 📸 9. Supporting Evidence

### 9.1 RAID Concepts

RAID architecture and storage redundancy concepts documented during the assignment.

![RAID Concepts](Screenshots/RAID-Concepts.png)

**Topics Demonstrated:**

- RAID levels and storage architecture.
- Performance and redundancy characteristics.
- Enterprise storage fundamentals.

### 9.2 Brocade Switch Configuration

Brocade SAN switch configuration workflow and administration concepts.

![Brocade Switch Configuration](Screenshots/Brocade-Switch-Configuration.png)

**Topics Demonstrated:**

- Brocade SAN switch management.
- Management configuration workflow.
- Storage networking administration.

### 9.3 Cisco SAN Configuration

Cisco SAN switch administration and management concepts.

![Cisco SAN Configuration](Screenshots/Cisco-SAN-Configuration.png)

**Topics Demonstrated:**

- Cisco SAN management workflow.
- Switch identification and management settings.
- Enterprise SAN administration concepts.

### 9.4 SAN Zoning Configuration

SAN zoning workflow for controlling host-to-storage communication.

![SAN Zoning Configuration](Screenshots/SAN-Zoning-Configuration.png)

**Topics Demonstrated:**

- SAN zoning principles.
- Host-to-storage connectivity.
- Storage access control.

---

## 🧠 10. Key Learning Outcomes

- Understood enterprise storage architecture.
- Compared RAID 0, RAID 1, and RAID 5.
- Studied multipathing and redundant storage connectivity.
- Differentiated block, file, and object storage.
- Understood SAN and Fibre Channel fundamentals.
- Reviewed Brocade and Cisco switch administration workflows.
- Explored SAN management using CLI and GUI interfaces.
- Understood WWN-based and port-based zoning.
- Studied host-to-storage access control.
- Learned NetBackup architecture components.
- Explored Rubrik policy-based data protection.
- Reviewed backup planning for virtual machines and physical servers.
- Compared full, incremental, differential, and synthetic backups.
- Understood NDMP backup concepts.
- Developed foundational knowledge of data protection, disaster recovery, and business continuity.

---

## 🚀 11. Lab Summary

This Storage & Backup capstone covered enterprise storage fundamentals, RAID configurations, multipathing, SAN architecture, Brocade and Cisco switch management, zoning, and enterprise backup solutions.

The first assignment introduced **RAID, multipathing, and block/file/object storage** concepts.

The second assignment explored **SAN switch administration, Fibre Channel connectivity, and zoning workflows**.

The third assignment covered **NetBackup, Rubrik, backup configuration planning, backup types, and NDMP**.

The documented assignments and supporting screenshots demonstrate foundational enterprise storage and data protection knowledge developed during **Cognizant CIS Multicloud technical training**.

These concepts provide a foundation for further learning in **cloud infrastructure, virtualization, storage administration, infrastructure operations, backup engineering, and DevOps engineering**.
