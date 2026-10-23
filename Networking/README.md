
# Networking Administration | Technical Capstone Lab

## 1. Overview

This module documents networking assignments completed
during the Cognizant CIS Multicloud technical training
program.

The activities covered network device configuration,
IP addressing, network segmentation, VLANs, inter-VLAN
routing, wireless networking, DHCP, DNS, network
classification, and connectivity troubleshooting.

The training combined network simulation exercises
with theoretical study of networking technologies
used in enterprise infrastructure environments.

## 2. Lab Environment & Technologies

| Component | Purpose |
|---|---|
| Router | Connects different IP networks |
| Layer 2 Switch | Forwards Ethernet frames using MAC addresses |
| Layer 3 Switch | Supports switching and IP routing |
| Wireless Access Point | Provides wireless network connectivity |
| Firewall | Controls network traffic according to security policies |
| Client Systems | Used for IP configuration and connectivity testing |
| Network Simulation Environment | Used to explore network topology and device configuration |
| CLI / Command Prompt | Used for device administration and connectivity verification |

### Protocols & Technologies Covered

- IPv4 addressing and subnetting
- Ethernet and switching
- VLANs and inter-VLAN routing
- DHCP and DNS
- ICMP and traceroute
- Wi-Fi and WPA3
- SNMP-independent basic network connectivity testing
- Network segmentation and access control concepts

## 3. Technical Objectives

- Understand the roles of common network devices.
- Design a basic wired and wireless network topology.
- Configure IP addressing and default gateways.
- Understand network segmentation and subnetting.
- Explore VLAN creation and inter-VLAN routing.
- Study VLAN security and wireless access control.
- Understand DHCP address pools and reservations.
- Explore DNS-based name resolution.
- Classify networks based on coverage and purpose.
- Practice router, switch, and client configuration.
- Verify network connectivity using diagnostic commands.

---

## 4. Assignment 1 — Network Device Configuration

### 4.1 Home / Lab Network Setup

**Objective:** Understand the components required
to build a small wired and wireless network.

The assignment covered a network consisting of:

- Router
- Switch
- Wireless Access Point
- Client devices

### Network Topology

```text
              Router
                |
              Switch
             /      \
            /        \
       Wired PC    Wireless AP
                       |
                  Wi-Fi Clients
```

This is a conceptual representation of the
network components studied in the assignment.

### 4.2 Network Device Functions

| Device | Function |
|---|---|
| Router | Connects separate networks and forwards IP packets |
| Switch | Connects devices within a local network |
| Wireless Access Point | Provides wireless access to the local network |
| Client | Communicates with other devices using network settings |

### 4.3 IP Addressing

IP addresses identify network interfaces and enable
communication between devices.

The assignment covered assigning IP addresses
and understanding the purpose of network segmentation.

### 4.4 Network Segmentation

Network segmentation divides a network into
smaller logical or physical sections.

Potential benefits include:

- Improved traffic organization
- Reduced broadcast-domain size when using VLANs
- More controlled communication between groups
- Easier network management

### 4.5 Connectivity Verification

The assignment covered two diagnostic utilities.

**Ping**

```bash
ping 192.168.1.1
```

Ping sends ICMP Echo Requests to test whether
the target responds.

**Traceroute**

On Windows:

```cmd
tracert 192.168.1.1
```

On Linux:

```bash
traceroute 192.168.1.1
```

Traceroute helps identify the network path
toward a destination, subject to device
and network filtering behavior.

The addresses above are illustrative commands
consistent with the lab's documented network.

### Technical Outcome

Explored basic network topology design,
device connectivity, IP addressing,
network segmentation, and troubleshooting.

---

## 5. Assignment 2 — VLAN & Wireless Network Configuration

### 5.1 VLAN Fundamentals

A Virtual Local Area Network (VLAN) divides
a switched network into separate logical
broadcast domains.

VLANs allow devices to be grouped logically
even when they share physical switching infrastructure.

### 5.2 VLAN Segmentation

**Conceptual Example**

```text
             Layer 3 Switch
               /        \
              /          \
          VLAN 10       VLAN 20
             |             |
         Department A  Department B
```

VLAN segmentation helps organize traffic
and provides a foundation for access control.

Devices in separate VLANs generally require
Layer 3 routing to communicate.

### 5.3 Inter-VLAN Routing

Inter-VLAN routing enables communication
between different VLANs.

The assignment covered routing between VLANs
using a router or Layer 3 switch.

**Technical Concepts:**

- VLAN interfaces
- Default gateways
- Layer 3 packet forwarding
- Controlled communication between subnets

### 5.4 VLAN Security Policies

The training covered VLAN-based network
segmentation and access restrictions.

Security concepts included:

- Separating network traffic
- Restricting unauthorized communication
- Protecting sensitive network segments
- Applying appropriate access-control policies

VLAN separation alone is not a complete
security control; traffic restrictions require
suitable routing and access-control configuration.

### 5.5 Wireless Network Configuration

The assignment covered configuring a wireless
network using WPA3 security concepts.

**Wireless Security Topics:**

- WPA3 encryption and authentication
- Secure wireless access
- Wireless network identification
- Guest and private network separation

### 5.6 SSID Configuration

An SSID identifies a wireless network.

| SSID Type | Intended Purpose |
|---|---|
| Private SSID | Access for authorized internal users |
| Guest SSID | Limited access for visitors or external users |

The assignment explored using separate SSIDs
to organize wireless access and improve
network security.

### Technical Outcome

Studied VLAN segmentation, inter-VLAN routing,
network access restrictions, WPA3 security,
and wireless SSID configuration.

---

## 6. Assignment 3 — DHCP & DNS Configuration

### 6.1 DHCP Overview

Dynamic Host Configuration Protocol (DHCP)
automatically provides IP configuration
to network clients.

Typical DHCP settings include:

- IP address
- Subnet mask
- Default gateway
- DNS server addresses

### 6.2 DHCP Address Pool

A DHCP pool defines the range of IP addresses
available for assignment to clients.

**Conceptual DHCP Workflow**

```text
        DHCP Client
             |
             | Address Request
             v
         DHCP Server
             |
             | IP Configuration
             v
        DHCP Client
```

The assignment covered creating DHCP address
pools for automatic IP allocation.

### 6.3 DHCP Reservation

A DHCP reservation associates a specific
client identifier, commonly a MAC address,
with a designated IP address.

Reservations are useful for devices requiring
predictable network addressing, such as:

- Printers
- Servers
- Network appliances

### 6.4 DNS Overview

Domain Name System (DNS) translates domain
names into corresponding resource records,
including IP addresses.

**Example**

```text
Domain Name: google.com
       |
       v
     DNS Query
       |
       v
   IP Address Result
```

DNS enables users and applications to
access resources using domain names
instead of memorizing IP addresses.

### 6.5 DHCP and DNS Integration

DHCP and DNS serve complementary purposes.

| Service | Responsibility |
|---|---|
| DHCP | Provides network configuration to clients |
| DNS | Resolves domain names and other DNS records |

Together, they simplify client network
configuration and resource access.

### Technical Outcome

Explored DHCP scope configuration,
automatic IP address allocation,
DHCP reservations, and DNS name resolution.

---

## 7. Assignment 4 — Network Type Classification

### 7.1 Network Types

The assignment covered network classification
based on geographical coverage,
connectivity technology, and usage.

| Network Type | Full Form | Description |
|---|---|---|
| LAN | Local Area Network | Connects devices within a limited area such as an office |
| WAN | Wide Area Network | Connects networks across large geographical distances |
| WLAN | Wireless Local Area Network | Provides wireless connectivity within a local area |
| MAN | Metropolitan Area Network | Connects networks across a city or metropolitan region |
| PAN | Personal Area Network | Connects personal devices over short distances |
| CAN | Campus Area Network | Connects networks across a campus or organization |
| SOHO | Small Office / Home Office | Describes a small office or home networking environment |

### 7.2 LAN

A LAN connects devices within a relatively
small geographical area.

**Examples:**

- Office networks
- Computer laboratories
- Home networks

Common technologies include Ethernet and Wi-Fi.

### 7.3 WAN

A WAN connects networks over larger
geographical distances.

**Examples:**

- Corporate branch connectivity
- Global enterprise networks
- The Internet

WAN connectivity can use public,
private, or service-provider networks.

### 7.4 WLAN

A WLAN uses wireless networking technologies
to connect devices within a local area.

**Common Components:**

- Wireless access points
- Wireless routers
- Laptops and mobile devices

**Advantages:**

- Device mobility
- Flexible deployment
- Reduced need for wired client connections

**Considerations:**

- Wireless interference
- Signal coverage
- Authentication and encryption

### 7.5 MAN

A MAN connects networks across a metropolitan area.

**Examples:**

- City-wide connectivity
- Networks spanning multiple locations within a city

### 7.6 PAN

A PAN connects personal devices over
short distances.

**Examples:**

- Bluetooth headphones
- Smartphones and smartwatches
- Personal device synchronization

### 7.7 CAN

A CAN connects multiple local networks
within a campus or organizational site.

**Examples:**

- University campuses
- Hospital campuses
- Corporate campuses

### 7.8 SOHO

A SOHO network supports the networking
requirements of a home office or small business.

Typical components include:

- Router or modem
- Ethernet switch
- Wireless access point
- PCs, laptops, and printers

SOHO networks commonly combine wired
and wireless connectivity.

### Technical Outcome

Developed an understanding of network types,
their coverage, architecture, applications,
and connectivity characteristics.

---

## 8. Assignment 5 — Network Device Configuration Simulation

### 8.1 Objective

Explore network device configuration
and verify connectivity between
simulated network components.

### 8.2 Devices Covered

| Device | Primary Function |
|---|---|
| Layer 2 Switch | Ethernet frame forwarding |
| Layer 3 Switch | Switching and IP routing |
| Router | Routing between IP networks |
| Firewall | Network traffic filtering and access control |
| Wireless Access Point | Wireless network connectivity |

### 8.3 Switch Configuration

The assignment documented the following workflow:

1. Select the switch in the simulation environment.
2. Open the **CLI** tab.
3. Enter configuration mode.
4. Assign a device hostname.
5. Save the configuration.

**Illustrative Cisco IOS Commands**

```text
enable
configure terminal
hostname SW1
end
copy running-config startup-config
```

These commands illustrate the configuration
workflow described in the assignment.

The hostname helps identify the device,
while saving the configuration preserves
changes for subsequent restarts.

### 8.4 Router Configuration

The assignment documented:

1. Opening the router CLI.
2. Configuring interface IP addressing.
3. Assigning a router hostname.
4. Saving the configuration.

**Illustrative Cisco IOS Commands**

```text
enable
configure terminal
hostname R1
interface gigabitEthernet 0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
end
copy running-config startup-config
```

The interface name is an example and
depends on the simulated router model.

The router's IP address allows it to
communicate with devices on the connected subnet.

### 8.5 Client IP Configuration

The original assignment documents the
following PC configuration:

| Parameter | Configuration |
|---|---|
| IP Address | `192.168.1.2` |
| Subnet Mask | `255.255.255.0` |
| Default Gateway | `192.168.1.1` |

**Configuration Workflow:**

1. Select the PC in the simulation.
2. Navigate to **Desktop → IP Configuration**.
3. Enter the IP address.
4. Configure the subnet mask.
5. Set the default gateway.

### 8.6 Connectivity Testing

The assignment tested connectivity
between the PC and router.

**Command**

```cmd
ping 192.168.1.1
```

**Technical Explanation:**

- The PC sends ICMP Echo Requests.
- The target router responds when reachable
  and configured to permit the requests.
- Successful replies demonstrate
  basic IP connectivity between the devices.

### Verification Result

The original assignment documents
successful ping communication.

The supporting screenshot captures
the network connectivity exercise.

### Technical Outcome

Explored switch and router configuration,
device identification, IPv4 settings,
default gateways, and connectivity testing.

---

## 9. Verification & Technical Results

| Assignment | Technical Coverage | Evidence / Learning |
|---|---|---|
| Network Device Configuration | Topology, IP addressing, ping and traceroute | Network topology and connectivity screenshots |
| VLAN & Wireless | VLAN segmentation, inter-VLAN routing, WPA3 and SSIDs | VLAN and wireless configuration screenshot |
| DHCP & DNS | Address pools, reservations and name resolution | DHCP/DNS screenshot |
| Network Classification | LAN, WAN, WLAN, MAN, PAN, CAN and SOHO | Conceptual study |
| Device Simulation | Router, switch, PC configuration and ping | Network simulation and ping screenshots |

The screenshots support the documented
networking assignments and selected
configuration and verification activities.

---

## 10. Supporting Evidence

### 10.1 Network Topology & Connectivity

Network topology setup and connectivity
between network components.

![Network Topology](Screenshots/Network-Topology-and-Ping.png)

### 10.2 Ping Verification

Command-line connectivity testing
between network devices.

![Connectivity Testing](Screenshots/Pinging-Output.png)

### 10.3 VLAN & Wireless Network Configuration

VLAN segmentation and wireless
network configuration activities.

![VLAN and Wireless Network Configuration](Screenshots/VLAN-and-SSID-Configuration.png)

### 10.4 DHCP & DNS Configuration

DHCP address allocation and
DNS configuration exercises.

![DHCP and DNS Configuration](Screenshots/DHCP-DNS-Configuration.png)

---

## 11. Key Learning Outcomes

- Understood network device roles and topology design.
- Practiced IP addressing and basic network configuration.
- Explored network segmentation and subnetting.
- Studied VLANs and inter-VLAN routing.
- Understood VLAN security and access-control concepts.
- Explored WPA3 and private/guest SSID configuration.
- Learned DHCP address allocation and reservations.
- Understood DNS name resolution.
- Classified LAN, WAN, WLAN, MAN, PAN, CAN, and SOHO networks.
- Explored router and switch CLI configuration.
- Practiced client IP configuration and default gateways.
- Used ping for connectivity verification.
- Strengthened network troubleshooting fundamentals.

---

## 12. Lab Summary

This networking capstone covered network device
configuration, IP addressing, VLANs, wireless networking,
DHCP, DNS, network classification, and network simulation.

The assignments combined practical network configuration
and connectivity verification with theoretical study
of enterprise networking concepts.

The documented exercises and supporting screenshots
demonstrate foundational networking knowledge relevant
to cloud infrastructure, network operations,
system administration, and DevOps engineering.
