
# 📊 Infrastructure Monitoring | SolarWinds & Microsoft SCOM

## 📌 1. Overview

This module documents infrastructure monitoring assignments completed during the **Cognizant CIS Multicloud technical capstone training program**.

The activities focused on network device monitoring, monitoring platform configuration, alert management, network traffic analysis, agent deployment, management packs, reporting, and service availability tracking.

The training covered two monitoring platforms:

- **SolarWinds Orion:** Network discovery, node monitoring, alert configuration, and dashboard-based visibility.
- **Microsoft System Center Operations Manager (SCOM):** Server monitoring, agent deployment, management packs, notifications, and reporting.

The assignments introduced monitoring workflows used in IT infrastructure operations, troubleshooting, and service management.

## 🛠️ 2. Tools & Technologies

| Technology / Tool | Purpose |
|---|---|
| SolarWinds Orion | Centralized infrastructure and network monitoring |
| SolarWinds NPM | Network Performance Monitor |
| SolarWinds NTA | Network Traffic Analyzer |
| Microsoft SCOM | Server and infrastructure monitoring |
| Windows Server | Monitoring platform environment |
| Microsoft SQL Server | Monitoring platform database services |
| SNMP | Network device monitoring and information collection |
| ICMP | Network connectivity and reachability checks |
| NetFlow | Network traffic flow analysis |
| Web Consoles | Monitoring dashboards and administration |

## 🎯 3. Technical Objectives

- Understand infrastructure monitoring architecture.
- Explore installation and configuration of monitoring tools.
- Discover and add network devices for monitoring.
- Understand SNMP and ICMP-based monitoring.
- Configure monitoring alerts and notifications.
- Analyze network traffic and bandwidth utilization.
- Explore SCOM management groups and monitoring agents.
- Import and configure management packs.
- Understand availability and performance reporting.
- Study SLA tracking and service monitoring concepts.

---

## ⚙️ 4. SolarWinds — Assignment 1: Installation & Configuration

### 4.1 SolarWinds Orion Installation

**Objective:** Set up SolarWinds Orion for centralized network monitoring.

The assignment documented the following steps:

1. Downloaded the SolarWinds Orion installer.
2. Installed the monitoring platform on a Windows Server or virtual machine.
3. Selected the required monitoring modules, including Network Performance Monitor (NPM).
4. Completed the installation wizard.
5. Accessed the Orion web console.

### 4.2 Orion Web Console

The assignment documented accessing the web console at:

```text
http://localhost:8787
```

This address represents the local console endpoint recorded in the training report.

The web console provides access to monitoring dashboards, managed devices, alerts, and administration settings.

### 4.3 Initial Configuration

The documented initial setup included:

- Completing the configuration wizard.
- Configuring the SQL Server database connection.
- Adding basic network information.
- Accessing the monitoring dashboard.
- Verifying the initial monitoring environment.

### Technical Outcome

Explored SolarWinds Orion installation, monitoring module selection, database configuration, and web console access.

---

## 🌐 5. SolarWinds — Assignment 2: Network Device Monitoring

### 5.1 Adding Network Devices

**Objective:** Discover and monitor network devices through SolarWinds Orion.

The assignment documented this workflow:

1. Opened the SolarWinds web console.
2. Navigated to **Settings → Manage Nodes**.
3. Selected **Add Node**.
4. Entered the target device's IP address.
5. Configured SNMP or ICMP monitoring settings.
6. Completed the device discovery and addition process.
7. Reviewed the monitored node.

### 5.2 SNMP & ICMP Monitoring

| Protocol | Monitoring Purpose |
|---|---|
| SNMP | Collect device information and supported performance metrics |
| ICMP | Check network reachability and response behavior |

SNMP is commonly used to retrieve supported network device metrics, while ICMP can help determine whether a device is reachable.

### 5.3 Monitoring Alerts

The assignment covered creating alert conditions for common infrastructure issues.

**Example Alert Conditions:**

| Alert Condition | Purpose |
|---|---|
| CPU utilization above 80% | Identify high resource usage |
| Device down | Detect loss of device availability |

### 5.4 Alert Configuration Workflow

The documented workflow included:

1. Navigating to **Alerts & Activity → Manage Alerts**.
2. Creating a monitoring alert.
3. Defining trigger conditions.
4. Reviewing notification options.
5. Configuring email or dashboard-based notifications.

### 5.5 Monitoring Dashboard

SolarWinds dashboards provide a centralized view of monitored infrastructure.

The training covered reviewing:

- Monitored network devices.
- Device availability.
- Network health information.
- Monitoring alerts and status indicators.

### Technical Outcome

Practiced network device addition and explored monitoring protocols, alert conditions, and dashboard-based infrastructure visibility.

---

## 📈 6. SolarWinds — Assignment 3: Network Traffic Analysis

### 6.1 Network Traffic Analyzer (NTA)

SolarWinds Network Traffic Analyzer is used to analyze network traffic flows and bandwidth usage.

It helps administrators understand traffic patterns and identify potential network bottlenecks.

### 6.2 NetFlow Monitoring

The assignment documented the following workflow:

1. Enable NetFlow monitoring.
2. Configure supported network devices to export traffic flow information.
3. Review traffic information through the monitoring dashboard.
4. Analyze bandwidth utilization and traffic patterns.

### 6.3 Traffic Analysis Concepts

| Metric / Concept | Purpose |
|---|---|
| Bandwidth Utilization | Understand network capacity usage |
| Top Applications | Identify applications generating network traffic |
| Top Talkers | Identify devices or endpoints generating significant traffic |
| Traffic Flows | Understand communication patterns |
| Network Bottlenecks | Identify possible congestion or performance constraints |

### Technical Outcome

Studied network traffic analysis, NetFlow monitoring, bandwidth utilization, and traffic visibility using SolarWinds NTA.

---

## 🖥️ 7. SCOM — Assignment 1: Installation & Initial Setup

### 7.1 Microsoft SCOM Overview

Microsoft System Center Operations Manager (SCOM) is an infrastructure monitoring platform used to monitor the health, availability, and performance of supported systems and applications.

### 7.2 SCOM Installation

The assignment documented:

1. Installing SCOM on Windows Server.
2. Selecting the Management Server role.
3. Configuring the SQL Server database.
4. Completing the installation workflow.

### 7.3 Initial Configuration

The documented initial setup included:

- Opening the SCOM Operations Console.
- Connecting to the management group.
- Reviewing the monitoring dashboard.
- Verifying access to monitoring information.

### 7.4 Management Group Concept

A SCOM management group organizes monitoring components and managed systems under a common administrative environment.

It supports centralized monitoring configuration, health information, and alert management.

### Technical Outcome

Explored SCOM architecture, installation, management server configuration, and monitoring console navigation.

---

## 🔗 8. SCOM — Assignment 2: Agent Deployment

### 8.1 Monitoring Agents

SCOM agents collect monitoring information from supported managed computers.

Agents enable the monitoring platform to observe system health and performance.

### 8.2 Agent Discovery & Deployment

The assignment documented this workflow:

1. Opened the SCOM Operations Console.
2. Navigated to **Administration → Device Management**.
3. Selected **Agent Managed**.
4. Opened the **Discovery Wizard**.
5. Specified target computers.
6. Initiated remote agent installation.
7. Reviewed the agent deployment results.

### 8.3 Agent-Based Monitoring

SCOM agents support monitoring of:

- System availability.
- Operating system health.
- Performance information.
- Monitored services and applications.
- Events and alerts defined by management packs.

### Verification Evidence

The assignment includes a screenshot documenting the SCOM agent deployment results.

### Technical Outcome

Explored managed computer discovery, agent deployment, and agent-based infrastructure monitoring.

---

## 📦 9. SCOM — Assignment 3: Management Packs

### 9.1 Management Pack Overview

Management Packs (MPs) define monitoring configurations for supported technologies.

They can contain:

- Monitoring rules.
- Health monitors.
- Discoveries.
- Alerts.
- Monitoring configuration elements.

### 9.2 Importing Management Packs

The documented workflow included:

1. Opening the SCOM Operations Console.
2. Navigating to **Administration → Management Packs**.
3. Importing relevant management packs.
4. Reviewing the imported monitoring configurations.

### 9.3 Management Packs Covered

| Management Pack | Monitoring Focus |
|---|---|
| Windows Server | Operating system health and performance |
| SQL Server | Database platform health and monitoring |

### 9.4 Custom Management Packs

The assignment also covered creating a custom management pack for specific monitoring requirements.

The documented activities included:

- Creating a custom management pack.
- Defining monitoring rules.
- Associating monitoring configurations with selected systems.

### Verification Evidence

The assignment contains a screenshot of the SCOM management packs interface.

### Technical Outcome

Explored management pack administration, monitoring rules, and customized infrastructure monitoring configurations.

---

## 🔔 10. SCOM — Assignment 4: Notifications & Reporting

### 10.1 Alert Notifications

SCOM notifications help administrators receive information about monitored events and issues.

The assignment covered:

1. Opening **Administration → Notifications**.
2. Reviewing notification configuration.
3. Configuring email notification concepts.
4. Creating subscriber groups.
5. Associating alerts with notification rules.

### 10.2 Notification Components

| Component | Purpose |
|---|---|
| Alert | Indicates a monitored condition requiring attention |
| Subscriber | Defines a notification recipient |
| Subscriber Group | Organizes multiple notification recipients |
| Notification Channel | Defines the method used to send notifications |
| Notification Subscription | Determines which alerts trigger notifications |

### 10.3 Reporting

The training covered using monitoring reports to evaluate infrastructure health and performance.

**Availability Reports**

Used to review:

- System uptime.
- System downtime.
- Service availability trends.

**Performance Reports**

Used to review:

- CPU utilization.
- Memory utilization.
- Response times.
- Performance trends.

### 10.4 SLA Tracking

A Service Level Agreement (SLA) defines agreed service expectations.

The assignment used an example availability target of:

```text
Target Availability: 99.9%
```

Monitoring reports can support evaluation of service performance against agreed targets.

An SLA target is a service objective, not a measured availability result.

### Technical Outcome

Studied monitoring notifications, subscriber management, reporting, and SLA-based service availability tracking.

---

## ✅ 11. Verification & Technical Results

| Area | Assignment Activity | Evidence / Coverage |
|---|---|---|
| SolarWinds Orion | Installation and initial setup | Documented configuration workflow |
| Network Monitoring | Adding network devices | Device addition screenshot |
| Monitoring Dashboard | Reviewing monitored devices | Dashboard screenshot |
| Alerts | CPU and device availability conditions | Monitoring alert screenshot |
| SolarWinds NTA | NetFlow and bandwidth analysis | Assignment documentation |
| SCOM Setup | Management server and console configuration | Assignment documentation |
| SCOM Agents | Managed computer discovery and agent deployment | Agent deployment screenshot |
| Management Packs | Importing and reviewing management packs | Management packs screenshot |
| Notifications | Email alerts, subscribers, notification rules | Assignment documentation |
| Reporting & SLA | Availability, performance and SLA concepts | Assignment documentation |

The capstone documents monitoring workflows and provides supporting screenshots for selected configuration and verification activities.

---

## 📸 12. Supporting Evidence

### 12.1 SolarWinds — Adding a Network Device

The screenshot documents adding a network device through SolarWinds Orion for monitoring.

![SolarWinds Added Network Device](Screenshots/SolarWinds%20%E2%80%94%20Added%20network%20device.png)

### 12.2 SolarWinds — Monitoring Dashboard

The screenshot displays the SolarWinds monitoring dashboard used to review network devices and monitoring status.

![SolarWinds Monitoring Dashboard](Screenshots/SolarWinds-%20Final%20monitoring%20dashboard.png)

### 12.3 Monitoring — Alert Result

The screenshot documents a monitoring alert result, supporting the alert-management exercise.

![Monitoring Alert Result](Screenshots/Monitoring-Alert%20result.png)

### 12.4 SCOM — Agent Deployment

The screenshot documents SCOM agent deployment results for managed computer monitoring.

![SCOM Agent Deployment](Screenshots/SCOM%20%E2%80%94%20Agent%20deployment%20result.png)

### 12.5 SCOM — Management Packs

The screenshot displays SCOM management packs used to define monitoring configurations and workflows.

![SCOM Management Packs](Screenshots/SCOM%20%E2%80%94%20Management%20packs.png)

---

## 🧠 13. Key Learning Outcomes

- Explored SolarWinds Orion installation and configuration.
- Practiced adding network devices for monitoring.
- Understood SNMP and ICMP monitoring fundamentals.
- Studied alert configuration for CPU utilization and device availability.
- Reviewed centralized infrastructure monitoring dashboards.
- Explored NetFlow-based network traffic analysis.
- Understood SolarWinds NTA bandwidth and traffic metrics.
- Studied SCOM architecture and management groups.
- Explored SCOM agent discovery and deployment.
- Understood management packs and monitoring rules.
- Studied alert notifications and subscriber configuration.
- Learned availability and performance reporting concepts.
- Understood SLA tracking and service availability metrics.

---

## 🚀 14. Lab Summary

This monitoring capstone covered SolarWinds Orion, Network Traffic Analyzer, and Microsoft System Center Operations Manager.

The assignments included monitoring platform setup, network device discovery, alert management, traffic analysis, agent deployment, management packs, notifications, reporting, and SLA concepts.

The documented exercises and supporting screenshots demonstrate foundational knowledge of infrastructure monitoring workflows relevant to IT operations, cloud infrastructure, and system administration.

The module strengthened understanding of monitoring, operational visibility, infrastructure health, and proactive issue identification.
