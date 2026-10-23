
# 🖥️ VMware & Hyper-V | Virtualization Administration Lab

## 📌 1. Overview

This module documents virtualization administration exercises completed during the **Cognizant CIS Multicloud technical capstone training program**.

The assignments focused on VMware ESXi installation, hypervisor configuration, management networking, user administration, datastore management, virtual machine operations, templates, deployment workflows, snapshots, and migration concepts.

The training introduced foundational virtualization technologies used in enterprise infrastructure and cloud environments.

**Assignments Covered:**

1. **Hypervisor Installation & Configuration:** VMware ESXi deployment, network configuration, remote management, user accounts, datastores, and virtual machine administration.
2. **Advanced Virtual Machine Management:** Templates, VM provisioning, startup and shutdown configuration, migration, snapshots, and storage concepts.

The provided lab documentation primarily covers VMware ESXi. Microsoft Hyper-V is included as a related virtualization technology, without claiming a separately verified Hyper-V deployment.

## 🛠️ 2. Lab Environment & Technologies

| Component | Technology / Tool |
|---|---|
| Hypervisor | VMware ESXi |
| Management Interface | VMware Host Client |
| Virtualization | Virtual Machines (VMs) |
| Virtual Storage | VMware Datastores |
| Networking | ESXi Management Network, Virtual Networking |
| Access Management | Local Users, Roles, Permissions |
| VM Provisioning | Templates and Deployment Workflows |
| VM Protection | Snapshots and Backup Concepts |
| VM Migration | VMware vMotion Concepts |
| Additional Technology | Microsoft Hyper-V Fundamentals |

## 🎯 3. Technical Objectives

- Understand Type 1 hypervisor architecture.
- Install and configure VMware ESXi.
- Configure ESXi management networking.
- Assign management IP addresses, DNS, and hostname settings.
- Access ESXi through VMware Host Client.
- Understand user accounts and role-based access control.
- Configure and manage virtual datastores.
- Create and administer virtual machines.
- Perform virtual machine power operations.
- Understand template-based VM provisioning.
- Review automated deployment workflows.
- Configure VM startup and shutdown behavior.
- Explore VMware migration technologies.
- Understand snapshots and backup strategies.
- Compare local and shared datastore architectures.
- Develop foundational VMware and Hyper-V knowledge.

---

## ⚙️ 4. Assignment 1 — Hypervisor Installation & Configuration

### 4.1 Understanding VMware ESXi

**Objective:** Understand VMware ESXi architecture and deploy a virtualization host.

VMware ESXi is a Type 1, or bare-metal, hypervisor designed to run virtual machines directly on physical server hardware.

It provides virtualization capabilities for computing, memory, storage, and networking resources.

**Conceptual Architecture:**

```text
             Virtual Machines
          +---------+---------+
          |         |         |
          v         v         v
         VM 1      VM 2      VM 3
          |         |         |
          +---------+---------+
                    |
                    v
             VMware ESXi
               Hypervisor
                    |
                    v
             Physical Server
          CPU | RAM | Storage
```

### 4.2 VMware ESXi Installation

The assignment covered installation and initial configuration of the ESXi hypervisor.

**Documented Workflow:**

1. Prepared the hypervisor installation environment.
2. Started the VMware ESXi installation process.
3. Selected the target installation storage.
4. Configured installation settings.
5. Completed the hypervisor installation.
6. Performed initial host configuration.
7. Prepared the host for remote administration.

**Technical Outcome:**

Introduced the installation workflow for deploying a VMware ESXi virtualization host.

### 4.3 ESXi Management Network Configuration

**Objective:** Configure the management network used to administer the ESXi host.

The assignment covered:

- Management network configuration.
- Static IP address assignment.
- DNS server configuration.
- Hostname configuration.
- Restarting management networking when required.

**Conceptual Management Network:**

```text
        Administrator Workstation
                  |
                  | HTTPS
                  v
            Management Network
                  |
                  v
             ESXi Host IP
                  |
                  v
          VMware Host Client
```

The management network enables authorized administrators to access and configure the hypervisor remotely.

### 4.4 Static IP Address Configuration

The assignment included configuring a static IP address for ESXi management.

**Purpose:**

- Provides a predictable management address.
- Supports remote administration.
- Simplifies host identification.
- Helps maintain consistent connectivity.

A static address is generally preferred for infrastructure management interfaces when appropriate to the network design.

### 4.5 DNS & Hostname Configuration

The assignment covered configuring DNS and hostname settings.

**DNS Configuration:**

Allows the ESXi host to resolve hostnames through configured DNS servers.

**Hostname Configuration:**

Provides a recognizable identity for the hypervisor.

Correct DNS configuration can support management tools and other infrastructure services.

### 4.6 Remote Management Using VMware Host Client

**Objective:** Access and administer the ESXi host through a web interface.

The VMware Host Client provides browser-based administration of an individual ESXi host.

**Typical Access Format:**

```text
https://<ESXi-Management-IP>/ui
```

**Management Capabilities:**

- View host information.
- Inspect available resources.
- Manage virtual machines.
- Configure networking.
- Manage datastores.
- Review host settings.

**Documented Activity:**

The assignment covered connecting to VMware Host Client and verifying remote administration functionality.

### 4.7 User Account Management

The assignment covered creating user accounts and reviewing access permissions.

**Administrative Activities:**

- Create local user accounts.
- Review authentication requirements.
- Assign appropriate roles and permissions.
- Understand access control.
- Restrict administrative operations according to user privileges.

### 4.8 Role-Based Access Control

Role-Based Access Control (RBAC) helps administrators manage permissions by assigning roles to users.

**Conceptual Example:**

| Role Category | Example Responsibility |
|---|---|
| Administrator | Full host administration |
| Read-Only User | View permitted infrastructure information |
| Limited Operator | Perform specifically authorized operations |

Actual available roles and privileges depend on the VMware product and configuration.

**Security Principle:**

Users should receive only the permissions necessary to perform their assigned responsibilities.

### 4.9 Datastore Configuration

**Objective:** Understand how ESXi organizes storage used by virtual machines.

A datastore provides a logical storage container for VM-related files.

It can store:

- Virtual machine configuration files.
- Virtual disks.
- Snapshot-related files.
- Other supported VM files.

**Documented Activities:**

1. Reviewed available storage devices.
2. Created or configured a datastore.
3. Inspected datastore properties.
4. Verified datastore availability.
5. Explored datastore management operations.

### 4.10 Virtual Machine Creation

The assignment covered creating virtual machines through the hypervisor management environment.

**Typical Provisioning Workflow:**

1. Start the VM creation process.
2. Specify the VM name.
3. Select guest operating system settings.
4. Allocate virtual CPU and memory.
5. Select a datastore.
6. Configure virtual disks.
7. Select virtual network connectivity.
8. Complete VM creation.

### 4.11 Virtual Machine Power Operations

The assignment covered VM lifecycle administration.

**Operations:**

- Power on a VM.
- Power off a VM.
- Access the VM console.
- Review VM state.
- Perform basic VM management.

A guest operating system shutdown is generally preferable to a forced power-off when the guest is responsive.

### 4.12 Remote VM Console Access

The VMware Host Client provides access to supported virtual machine console operations.

**Administrative Uses:**

- Monitor VM startup.
- Interact with the guest operating system.
- Inspect console output.
- Perform initial configuration.
- Troubleshoot guest connectivity issues.

### Technical Outcome

Explored VMware ESXi installation, management networking, remote administration, user permissions, datastores, and virtual machine lifecycle operations.

---

## 🚀 5. Assignment 2 — Advanced Virtual Machine Management

### 5.1 Understanding VM Templates

**Objective:** Understand standardized virtual machine provisioning.

A VM template is a reusable virtual machine configuration used to deploy additional virtual machines with consistent settings.

**Benefits:**

- Standardized deployments.
- Reduced repetitive configuration.
- Faster VM provisioning.
- Consistent operating system baselines.
- Improved administration efficiency.

### 5.2 Template Creation Workflow

The assignment covered converting or preparing virtual machines for template-based deployment.

**Conceptual Workflow:**

```text
          Base Virtual Machine
                   |
                   v
          Configure OS & Tools
                   |
                   v
          Prepare Standard Image
                   |
                   v
             VM Template
                   |
                   v
          Deploy New Virtual VM
```

Template capabilities depend on the VMware management environment. Native vSphere templates are typically managed through vCenter Server rather than the standalone ESXi Host Client.

### 5.3 Automated VM Deployment

The training covered deploying virtual machines using prepared templates.

**Provisioning Concepts:**

1. Select an existing template.
2. Specify the new virtual machine name.
3. Select the destination host or resource.
4. Select the datastore.
5. Configure applicable guest settings.
6. Deploy the virtual machine.
7. Review the resulting VM configuration.

**Benefits:**

- Faster provisioning.
- Repeatable configurations.
- Reduced manual setup.
- Improved deployment consistency.

The supplied documentation does not establish that a separate automation script or Infrastructure as Code tool was used.

### 5.4 VM Startup & Shutdown Configuration

**Objective:** Understand how virtual machine startup and shutdown operations can be managed.

The assignment covered:

- Configuring VM startup behavior.
- Reviewing startup order.
- Configuring shutdown sequences.
- Managing VM power operations.

**Conceptual Startup Sequence:**

```text
              ESXi Host Starts
                     |
                     v
            Infrastructure VM
                     |
                     v
              Database VM
                     |
                     v
             Application VM
```

Startup sequencing can be useful when workloads have service dependencies.

Available automatic startup features depend on the VMware host and management configuration.

### 5.5 Virtual Machine Migration

The assignment introduced virtual machine migration concepts.

Migration involves moving a virtual machine or its components between supported infrastructure resources.

**Concepts Covered:**

- Virtual machine relocation.
- Host-to-host migration.
- Storage migration concepts.
- Workload mobility.
- VMware vMotion.

### 5.6 Understanding VMware vMotion

VMware vMotion enables supported running virtual machines to migrate between compatible ESXi hosts with minimal service interruption.

**Conceptual Architecture:**

```text
             ESXi Host A
                  |
              Running VM
                  |
                  | vMotion
                  v
             ESXi Host B
                  |
              Running VM
```

**Potential Benefits:**

- Workload mobility.
- Maintenance flexibility.
- Infrastructure resource management.
- Reduced planned downtime.

**Important:**

vMotion requires a compatible VMware environment and appropriate configuration.

The assignment covered vMotion concepts and migration workflows where supported; a completed live migration is not independently verified by the supplied evidence.

### 5.7 VM Snapshot Management

**Objective:** Understand how snapshots preserve a VM state for supported rollback operations.

A VMware snapshot can capture virtual machine disk state and, depending on options, memory state.

**Conceptual Workflow:**

```text
           Virtual Machine
                  |
                  v
           Create Snapshot
                  |
                  v
          Perform VM Changes
                  |
             +----+----+
             |         |
             v         v
         Continue    Revert to
         Changes     Snapshot
```

### 5.8 Snapshot Use Cases

- Preparing for configuration changes.
- Testing software updates.
- Supporting temporary rollback scenarios.
- Capturing a known VM state before maintenance.

**Important Technical Distinction:**

A snapshot is **not a substitute for a backup**.

Snapshots typically depend on the original VM disks and datastore. They do not independently protect against the loss of the underlying storage.

Long-running snapshots can also introduce storage and performance considerations.

### 5.9 Virtual Machine Backup Strategies

The assignment covered VM backup and recovery concepts.

**Backup Planning Considerations:**

- Protected virtual machines.
- Backup frequency.
- Backup storage location.
- Retention policies.
- Recovery requirements.
- Restore verification.

**Conceptual Backup Workflow:**

```text
             Virtual Machine
                    |
                    v
              Backup Process
                    |
                    v
           Independent Backup
               Repository
                    |
                    v
              VM Restoration
```

The provided evidence documents snapshot management and backup concepts, not a separately verified successful backup-and-restore job.

### 5.10 Local Datastore Concepts

Local datastores use storage resources attached to or directly available to an ESXi host.

**Characteristics:**

- Host-associated storage.
- Can support virtual machine files.
- May be simpler to configure in a lab.
- Does not automatically provide shared storage access to other hosts.

### 5.11 Shared Datastore Architecture

Shared storage can be accessible to multiple compatible ESXi hosts.

**Common Technologies:**

- Fibre Channel SAN.
- iSCSI storage.
- NFS datastores.
- Supported shared storage platforms.

**Conceptual Architecture:**

```text
          ESXi Host A       ESXi Host B
               |                |
               +--------+-------+
                        |
                        v
                 Shared Storage
                        |
                        v
                     Datastore
```

Shared storage can support certain clustering and migration architectures when the remaining VMware requirements are satisfied.

### 5.12 Local vs. Shared Storage

| Feature | Local Datastore | Shared Datastore |
|---|---|---|
| Storage Access | Associated with a host | Accessible to multiple configured hosts |
| Typical Environment | Standalone or lab host | Multi-host infrastructure |
| Configuration | Often simpler | Requires supported storage connectivity |
| Migration Support | Depends on migration method | Supports certain multi-host migration scenarios |
| Availability | Depends on host and storage design | Depends on shared storage and infrastructure design |

### Technical Outcome

Explored VM templates, deployment workflows, startup and shutdown management, migration, snapshots, backup strategies, and local versus shared datastore architectures.

---

## 🔄 6. Microsoft Hyper-V — Related Virtualization Fundamentals

### 6.1 Hyper-V Overview

Microsoft Hyper-V is a virtualization platform that enables Windows-based systems to host and manage virtual machines.

Like VMware ESXi, Hyper-V provides virtualized computing resources for guest operating systems.

### 6.2 VMware ESXi vs. Hyper-V

| Feature | VMware ESXi | Microsoft Hyper-V |
|---|---|---|
| Platform | VMware hypervisor | Microsoft hypervisor |
| Management | Host Client, vCenter | Hyper-V Manager, PowerShell, Windows Admin Center |
| Virtual Machines | VMware VM formats | Hyper-V VM formats |
| Virtual Networking | VMware virtual switches | Hyper-V virtual switches |
| Checkpoint / Snapshot | VM Snapshots | VM Checkpoints |
| Migration | vMotion and supported migration methods | Live Migration and supported migration methods |

### 6.3 Hyper-V Concepts

Related virtualization topics include:

- Virtual machine creation.
- Virtual processors and memory.
- Virtual switches.
- VM checkpoints.
- Virtual disks.
- Virtual machine lifecycle operations.
- Live migration concepts.

**Coverage Note:**

These are related virtualization fundamentals. The six screenshot references provided for this module document VMware-focused activities, so this section does not claim a separate completed Hyper-V practical lab.

---

## 🧩 7. Virtualization Architecture & Infrastructure Concepts

### 7.1 Virtualization Components

| Component | Function |
|---|---|
| Hypervisor | Runs and manages virtual machines |
| Virtual Machine | Provides an isolated guest computing environment |
| vCPU | Virtualized processor resources |
| vRAM | Memory allocated to a VM |
| Virtual Disk | VM storage device |
| Virtual Switch | Connects virtual network interfaces |
| Datastore | Stores virtual machine files |
| Snapshot | Preserves a point-in-time VM state for supported rollback |
| Template | Supports standardized VM provisioning |

### 7.2 Virtual Networking

Virtual networking connects virtual machines to each other and, when configured, to physical networks.

**Conceptual Architecture:**

```text
                Physical Network
                       |
                       v
                Physical NIC
                       |
                       v
                 Virtual Switch
                  /          \
                 v            v
               VM 1          VM 2
```

### 7.3 Benefits of Virtualization

- Improved hardware utilization.
- Consolidation of multiple workloads.
- Flexible virtual machine provisioning.
- Simplified lab environments.
- Resource allocation flexibility.
- Support for cloud infrastructure architectures.
- Improved workload management capabilities.

---

## ✅ 8. Assignment Review & Verification

| Assignment Activity | Technical Coverage | Evidence |
|---|---|---|
| ESXi Installation | Hypervisor deployment and initial setup | ESXi installation screenshot |
| Management Networking | IP, DNS, hostname, management access | Network configuration screenshot |
| Datastore Management | Storage configuration and availability | Datastore screenshot |
| VM Management | VM creation and power operations | VM management screenshot |
| VM Templates | Template preparation and conversion | Template screenshot |
| VM Snapshots | Snapshot operations | Snapshot screenshot |
| VM Migration | vMotion and migration workflows | Conceptual coverage |
| VM Backup | Backup and recovery strategies | Conceptual coverage |
| Hyper-V | Related virtualization fundamentals | No separate screenshot provided |

The screenshots document selected VMware administration activities. Other concepts are included based on the training description and should not be interpreted as proof of production deployment.

---

## 📸 9. Supporting Evidence

### 9.1 VMware ESXi Installation

Hypervisor installation and initial host setup.

![VMware ESXi Installation](Screenshots/ESXi-Installation.png)

**Activities Demonstrated:**

- VMware ESXi installation.
- Hypervisor deployment.
- Initial host setup.

### 9.2 Management Network Configuration

ESXi management network settings.

![Network Configuration](Screenshots/Network-Configuration.png)

**Activities Demonstrated:**

- Management network configuration.
- Static IP assignment.
- DNS and hostname configuration.
- Remote administration preparation.

### 9.3 Datastore Configuration

Virtualization storage management.

![Datastore Configuration](Screenshots/Datastore-Configuration.png)

**Activities Demonstrated:**

- Datastore creation.
- Storage configuration.
- Datastore administration.

### 9.4 Virtual Machine Management

VM creation and lifecycle administration.

![Virtual Machine Management](Screenshots/VM-Management.png)

**Activities Demonstrated:**

- Virtual machine creation.
- Power operations.
- Remote console access.
- Basic VM administration.

### 9.5 VM Template Creation

Template preparation and deployment concepts.

![VM Template Creation](Screenshots/VM-Template-Conversion.png)

**Activities Demonstrated:**

- Template creation or conversion workflow.
- Standardized VM provisioning.
- Template-based deployment concepts.

### 9.6 Snapshot Management

Virtual machine snapshot administration.

![Snapshot Management](Screenshots/Snapshot-Management.png)

**Activities Demonstrated:**

- Snapshot creation and management.
- VM rollback concepts.
- Virtual machine state management.

---

## 🧠 10. Key Learning Outcomes

- Understood Type 1 hypervisor architecture.
- Practiced VMware ESXi installation and configuration.
- Explored ESXi management network administration.
- Reviewed static IP, DNS, and hostname settings.
- Used VMware Host Client for remote administration.
- Studied user accounts, roles, and permissions.
- Explored datastore creation and management.
- Practiced virtual machine lifecycle operations.
- Understood VM templates and standardized provisioning.
- Reviewed startup and shutdown configuration.
- Studied vMotion and migration concepts.
- Explored VM snapshots and rollback.
- Understood the difference between snapshots and backups.
- Compared local and shared datastore architectures.
- Reviewed Microsoft Hyper-V fundamentals.
- Strengthened foundational virtualization and cloud infrastructure knowledge.

---

## 🚀 11. Lab Summary

This virtualization capstone covered VMware ESXi installation, host administration, management networking, datastores, virtual machine operations, templates, snapshots, and advanced VM management concepts.

The first assignment focused on **hypervisor deployment and foundational ESXi administration**.

The second assignment introduced **VM provisioning, templates, migration, snapshot management, and backup strategies**.

The module also relates these concepts to Microsoft Hyper-V as an additional enterprise virtualization platform.

The documented configuration activities and supporting screenshots demonstrate foundational VMware administration skills developed during **Cognizant CIS Multicloud technical training**.

These skills provide a foundation for further learning in **virtualization engineering, cloud infrastructure, systems administration, infrastructure automation, and DevOps engineering**.
