# Metropolitan Area Network Infrastructure — Chapin Red

Academic project developed for the **Computer Networks 2** course at the Universidad de San Carlos de Guatemala (First Semester 2026).

This repository contains the design, simulation, and configuration files for a high-availability Metropolitan Area Network (MAN) connecting two enterprise campus buildings through a redundant ring core in **Cisco Packet Tracer**.

---

## Overview

The "Chapin Red" project integrates Layer 2 switching and Layer 3 dynamic routing technologies into a secure, fault-tolerant enterprise infrastructure. Key mechanisms include VLAN segmentation with VTP, trunking over IEEE 802.1Q, EtherChannel link aggregation (LACP and PAgP), dynamic routing via OSPFv2 Area 0, centralized DHCP services with IP Helper relays, and extended Access Control Lists (ACLs) for perimeter security.

---

## Architecture and Topology

```
                  +-----------------------------------+
                  |      MAN Core Ring (Area 0)       |
                  |         (Dynamic OSPFv2)          |
                  +-----------------+-----------------+
                                    |
          +-------------------------+-------------------------+
          |                                                   |
          v                                                   v
+-----------------------+                           +-----------------------+
|   Building A (West)   |                           |   Building B (East)   |
| ├── Switched VLANs    |                           | ├── Switched VLANs    |
| ├── LACP EtherChannel |                           | ├── PAgP EtherChannel |
| ├── SVI Layer 3 GW    |                           | ├── SVI Layer 3 GW    |
| └── Extended ACLs     |                           | └── Extended ACLs     |
+-----------------------+                           +-----------------------+
          |                                                   |
          +-------------------------+-------------------------+
                                    |
                                    v
                     [ Centralized DHCP & DNS Server ]
```

---

## Key Features

- **Layer 2 Segmentation:** Structured VLAN allocation and VTP domain management.
- **Link Aggregation:** LACP (802.3ad) in West Campus and PAgP in East Campus for bandwidth multiplication and redundancy.
- **Dynamic Routing:** Single-area OSPFv2 over the metropolitan backbone ensuring sub-second route convergence.
- **Address Management:** Centralized DHCP server with IP Helper-Address relay configuration across all distribution switches.
- **Perimeter Security:** Granular inbound and outbound extended ACLs restricting sensitive administrative and server VLAN access.

---

## Technologies

- Cisco Packet Tracer
- Protocols: OSPFv2, VTP, IEEE 802.1Q, LACP, PAgP, DHCP Relay, ICMP, ARP
- Security: Extended ACLs, Port Security

---

## Repository Structure

```
REDES2_1S2026_202201336/
├── Proyecto1/
│   ├── Proyecto1_202201336.pkt    # Cisco Packet Tracer simulation file
│   └── Manual_Tecnico.md          # In-depth technical specification
├── imagenes/                      # Topology captures and verification ping tests
└── README.md
```

---

## Academic Context

| Field       | Detail                                         |
|-------------|------------------------------------------------|
| Course      | Computer Networks 2 (REDES2)                   |
| Institution | Universidad de San Carlos de Guatemala         |
| Semester    | First Semester 2026                            |
| Author      | Estuardo Josue Vaquiax Reyes (202201336)       |
