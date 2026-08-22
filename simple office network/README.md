# Simple Office Network – Cisco Packet Tracer

## 📌 Project Overview

This project demonstrates the design and configuration of a **simple office network** using **Cisco Packet Tracer**.

The network is designed to connect multiple office computers through a network switch and provide basic communication between the connected devices.

The project focuses on understanding how devices in a small office environment are connected, configured, and tested.

## 🎯 Objectives

- Design a basic office network topology
- Connect multiple computers using a network switch
- Configure IP addresses for the connected devices
- Understand communication within a Local Area Network (LAN)
- Test connectivity between network devices
- Gain hands-on experience with Cisco Packet Tracer

## 🖥️ Network Topology

The basic network follows a structure similar to:

```text
              ┌─────────────┐
              │   Switch    │
              └──────┬──────┘
               ┌─────┼─────┐
               │     │     │
              PC1   PC2   PC3
               │     │     │
              PC4   PC5   PC6
```

The switch acts as the central device that connects the computers within the office LAN.

## ⚙️ Configuration

The computers are configured with IP addresses belonging to the same network so that they can communicate with each other.

Example:

| Device | IP Address |
|---|---|
| PC1 | 192.168.1.1 |
| PC2 | 192.168.1.2 |
| PC3 | 192.168.1.3 |
| PC4 | 192.168.1.4 |

> The exact IP addresses and number of devices may vary depending on the Packet Tracer topology.

## 🧪 Connectivity Testing

After configuring the devices, connectivity is tested using the `ping` command.

Example:

```text
PC1 → ping 192.168.1.2
```

A successful reply confirms that the devices can communicate through the LAN.

## 📚 Networking Concepts Practiced

- Local Area Network (LAN)
- Network topology
- Ethernet
- Switches
- IP addressing
- Subnet mask
- MAC addresses
- Basic device configuration
- ICMP / `ping`
- Connectivity testing

## 🛠️ Tool Used

**Cisco Packet Tracer**

The original project file is provided as:

```text
simple office network.pkt
```

Open the `.pkt` file with Cisco Packet Tracer to view the complete topology and device configuration.

## 📈 Learning Outcome

Through this project, I gained practical experience in creating a small office LAN, configuring end devices, connecting devices through a switch, and verifying network connectivity.

This project is part of my ongoing journey in **Computer Networking and Network Engineering**.

## 🚀 Future Improvements

Possible improvements to this network include:

- Adding a router
- Implementing DHCP
- Creating multiple VLANs
- Configuring inter-VLAN routing
- Adding a server
- Implementing network security using ACLs
- Adding wireless connectivity
- Monitoring network performance
- Automating network configuration using Python

---

**Part of my hands-on Computer Networking learning journey. 🌐**
