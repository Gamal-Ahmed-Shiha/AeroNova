# ✈️ AeroNova: A Scalable Airport Network 🛫

![AeroNova Banner](https://img.shields.io/badge/Project-AeroNova-blue?style=for-the-badge&logo=airbus)
![Cisco Packet Tracer](https://img.shields.io/badge/Tool-Cisco%20Packet%20Tracer-orange?style=for-the-badge&logo=cisco)
![Network Design](https://img.shields.io/badge/Type-Enterprise%20Network-green?style=for-the-badge)

> **"A Gateway To Every Journey"**  
> An airport connects travelers with destinations through organized services, convenient facilities, clear information, and a smooth journey from arrival to departure.

## 📖 Overview

**AeroNova** is a comprehensive, scalable network topology designed for a modern airport environment. This project simulates the complex networking requirements of a busy airport, including management segregation, public wireless access, hall-specific services, and centralized server management.

This project was designed to demonstrate skills in **VLAN segmentation**, **Inter-VLAN routing**, **DHCP/DNS configuration**, and **static & dynamic routing** using Cisco Packet Tracer.

---

## 👥 Team & Supervision

**Project Creators:**
*   Gamal Ahmed Shiha
*   Ahmed Abdalrhman Ibrahim
*   Ahmed Ashraf Mohamed
*   Ahmed Mohammed Kamel
*   Ahmed Tamer Ahmed
*   Hagar Tmmam Imamm
*   Mostafa Ahmed Salah Mahdi
*   Walaa Magdy Salah Abdelfatah

**Supervised By:**
*   **Dr. Aya Magdy**

---

## 🗺️ Network Topology & Architecture

The network is divided into distinct functional zones to ensure security, scalability, and ease of management.

### 🏢 Main Zones
1.  **Server Room:** Centralized infrastructure hosting core services.
2.  **Management (Left & Right):** Administrative devices separated into two distinct subnets for load balancing and organization.
3.  **Passenger Halls (1, 2, & 3):** Public areas segmented by VLANs, each with its own dedicated Web Server.
4.  **Wireless Access:** Coverage for management staff and security teams.

### 🧠 Core Components
*   **Multilayer Switch (3560):** Acts as the core switch, handling Inter-VLAN routing and acting as the gateway for all subnets.
*   **Routers (ISR 4331):** Used for WAN simulation and connecting the Management and Server zones.

---

## 📊 Subnetting & Addressing Scheme

The addressing scheme uses the private `10.20.x.x` range with a consistent `/24` subnet mask. This provides **254 usable addresses** per location, ensuring scalability.

| Zone / Subnet | Network Address | Mask | Gateway | Description |
| :--- | :--- | :--- | :--- | :--- |
| **Server's Room** | `10.20.30.0` | `/24` | `10.20.30.254` | Core servers (DHCP, DNS, Web, Email, FTP, NTP) |
| **Left Management** | `10.20.40.0` | `/24` | `10.20.40.254` | Admin devices on the left wing |
| **Right Management** | `10.20.50.0` | `/24` | `10.20.50.254` | Admin devices on the right wing |
| **Hall 1** | `10.20.60.0` | `/24` | `10.20.60.254` | Public/VLAN for Hall 1 |
| **Hall 2** | `10.20.70.0` | `/24` | `10.20.70.254` | Public/VLAN for Hall 2 |
| **Hall 3** | `10.20.80.0` | `/24` | `10.20.80.254` | Public/VLAN for Hall 3 |

---

## ⚙️ Essential Network Services

The AeroNova network implements a robust set of services to ensure smooth operations:

*   **🔌 DHCP (Dynamic Host Configuration Protocol):** Automatically assigns IP addresses, subnet masks, gateways, and DNS servers to all devices across different VLANs.
*   **🌐 DNS & Web Hosting:**
    *   **DNS:** Translates domain names into IP addresses.
    *   **Web Servers:** Each Hall (1, 2, 3) has its own dedicated Web Server hosting flight information specific to that hall.
*   **📧 FTP & Email Services:** Secure file transfer between users and internal email communication.
*   **⏰ NTP (Network Time Protocol):** Synchronizes date and time across all network devices for accurate logging and security events.
*   **📡 Wireless Connectivity:**
    *   **Management Subnets:** Flexible connectivity for staff.
    *   **Smart Area 1 & 2:** High-density wireless for security teams' mobile devices.
    *   **Mobility:** Seamless roaming between halls.

---

## 🔐 VLANs & Inter-VLAN Routing

To improve network organization, isolation, and traffic management:

*   **VLAN Segmentation:** Each airport hall and management area is assigned a separate VLAN.
*   **Multilayer Switching:** The core Multilayer Switch (3560) provides **Inter-VLAN Routing**. This allows users from different Hall VLANs to communicate with and access Web Servers of other halls when needed, while maintaining logical separation.
*   **Security:** This design prevents broadcast storms from affecting the entire airport and isolates sensitive management traffic from public hall traffic.

---

## 🛠️ Configuration Highlights

### Router & Switch Configuration
*   **Router1 & Router2:** Configured with Serial connections to simulate WAN links between Left/Right management and the Server room.
*   **Multilayer Switch:** Configured with `ip routing` enabled. SVIs (Switch Virtual Interfaces) created for each VLAN to act as the default gateway.
*   **Trunking:** 802.1Q trunks configured between switches to carry multiple VLANs.

### Wireless Configuration
*   **APs:** Registered to the WLC and placed in the Smart Areas to provide coverage for security personnel.

---

## 🚀 How to Use This Repository

1.  **Download** the `.pkt` file from the repository.
2.  **Open** it using **Cisco Packet Tracer** (Version 8.0 or higher recommended).
3.  **Explore** the topology. You can click on PCs and Smartphones to see their DHCP assignments.
4.  **Test Connectivity:** Use the Ping tool from a PC in Hall 1 to a Server in the Server Room (`10.20.30.x`).
5.  **Web Access:** Open the Web Browser on any PC and enter the IP address of a Hall Web Server to see the flight information page.
<p align="center">
  <b>Safe Travels! ✈️</b>
</p>
