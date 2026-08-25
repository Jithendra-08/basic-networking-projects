# Multi-Department Enterprise Network – Cisco Packet Tracer

## 📌 Project Overview

This project simulates a small enterprise network with three departments:

- Admin
- Finance
- CS

Each department is separated using VLANs and assigned its own IP subnet. A Cisco router provides inter-VLAN routing and DHCP, while a switch connects the end devices.

The simulation includes wired and wireless devices such as PCs, laptops, and smartphones.

## 🎯 Objectives

- Create separate VLANs for different departments
- Configure switch access ports
- Configure a trunk link between the switch and router
- Implement Router-on-a-Stick
- Enable inter-VLAN routing
- Configure DHCP on the router
- Automatically assign IP addresses to clients
- Connect wired and wireless devices
- Test network connectivity

## 🏗️ Network Topology

```text
                         ┌─────────────────────┐
                         │       ROUTER        │
                         │ DHCP + Inter-VLAN   │
                         │      Routing        │
                         └──────────┬──────────┘
                                    │
                              802.1Q TRUNK
                                    │
                         ┌──────────┴──────────┐
                         │       SWITCH        │
                         └──────────┬──────────┘
                                    │
              ┌─────────────────────┼─────────────────────┐
              │                     │                     │
           VLAN 10               VLAN 20               VLAN 30
            ADMIN                FINANCE                   CS
              │                     │                     │
          Fa0/2-4               Fa0/5-7               Fa0/8-10
              │                     │                     │
        PCs / Laptops         PCs / Laptops         PCs / Laptops
        / Smartphones        / Smartphones        / Smartphones
```

## 🌐 VLAN and IP Addressing

| Department | VLAN ID | Network | Default Gateway |
|---|---:|---|---|
| Admin | 10 | `192.168.1.0/26` | `192.168.1.1` |
| Finance | 20 | `192.168.1.64/26` | `192.168.1.65` |
| CS | 30 | `192.168.1.128/26` | `192.168.1.129` |

Each `/26` subnet provides 64 total addresses and 62 usable host addresses.

## 🔌 Switch Port Configuration

| Switch Port | VLAN | Purpose |
|---|---:|---|
| Fa0/1 | Trunk | Connection to router |
| Fa0/2 – Fa0/4 | 10 | Admin devices |
| Fa0/5 – Fa0/7 | 20 | Finance devices |
| Fa0/8 – Fa0/10 | 30 | CS devices |

## 🔀 Router-on-a-Stick

The router uses subinterfaces on `GigabitEthernet0/0`:

| Subinterface | VLAN | IP Address |
|---|---:|---|
| `G0/0.10` | 10 | `192.168.1.1/26` |
| `G0/0.20` | 20 | `192.168.1.65/26` |
| `G0/0.30` | 30 | `192.168.1.129/26` |

802.1Q encapsulation identifies VLAN traffic across the trunk.

## 📡 DHCP

The router is configured as a DHCP server for all three departments.

| DHCP Pool | Network | Gateway |
|---|---|---|
| Admin-pool | `192.168.1.0/26` | `192.168.1.1` |
| Finance-Pool | `192.168.1.64/26` | `192.168.1.65` |
| CS-Pool | `192.168.1.128/26` | `192.168.1.129` |

DHCP automatically provides clients with their IP address, subnet mask, default gateway, and DNS information.

## 🔄 How the Network Works

Devices in the same VLAN communicate through the switch.

When a device needs to communicate with another VLAN, traffic is sent to its default gateway and routed by the router.

```text
Admin VLAN 10
      ↓
Switch
      ↓
802.1Q Trunk
      ↓
Router
      ↓
Finance VLAN 20
```

This is called **inter-VLAN routing**.

## 🧪 Verification Commands

```text
show vlan brief
show interfaces trunk
show ip interface brief
show ip dhcp pool
show ip dhcp binding
show spanning-tree
```

Connectivity can be tested with:

```text
ping <destination-ip>
```

## ✅ Verification

DHCP leases were successfully obtained by devices in all three departments.

Example:

```text
Admin:
192.168.1.2
192.168.1.3
192.168.1.4
192.168.1.5

Finance:
192.168.1.66
192.168.1.67
192.168.1.68
192.168.1.70

CS:
192.168.1.130
192.168.1.131
192.168.1.132
192.168.1.133
```

## 🧠 Concepts Demonstrated

- LAN and network topology
- VLAN segmentation
- Access ports
- Trunk ports
- IEEE 802.1Q
- Router-on-a-Stick
- Inter-VLAN routing
- IPv4 addressing
- `/26` subnetting
- Default gateways
- DHCP
- DHCP pools and leases
- DNS configuration
- MAC addressing
- Spanning Tree Protocol
- Wireless networking
- Network troubleshooting
- Connectivity testing

## 🛠️ Tools and Technologies

- Cisco Packet Tracer
- Cisco IOS CLI
- IPv4
- Ethernet
- Wi-Fi
- VLAN
- DHCP
- IEEE 802.1Q

## 📂 Project File

Open the `.pkt` file using Cisco Packet Tracer to view the complete topology and configuration.

## 🚀 Possible Future Improvements

- Access Control Lists (ACLs)
- NAT and Internet connectivity
- DNS and Web servers
- SSH remote management
- Switch port security
- EtherChannel
- Network redundancy
- Network monitoring
- Python-based network automation
- AI-based network monitoring and anomaly detection
