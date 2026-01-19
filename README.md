📘 Cisco ACL & VLAN Lab
A hands‑on networking project demonstrating VLAN segmentation, trunking, Router‑on‑a‑Stick, DHCP services, inter‑VLAN routing, and ACL‑based traffic filtering using Cisco Packet Tracer.

This lab was built and tested using a Cisco 2960 switch, a router, and two PCs connected through FastEthernet interfaces.

🧱 Topology Overview
Devices used:

1× Cisco Router

1× Cisco 2960 Switch

2× PCs

FastEthernet and GigabitEthernet connections

High‑level design:

VLAN 10 (HOME)

VLAN 20 (LAB)

Trunk link between switch and router

Router‑on‑a‑Stick for inter‑VLAN routing

DHCP pools for each VLAN

ACL blocking VLAN 20 → VLAN 10

A full Packet Tracer file is included in the lab/ folder.

📂 Repository Structure
Code
Cisco-ACL-VLAN-Lab/
├── README.md
├── configs/
│   ├── router-config.txt
│   └── switch-config.txt
├── screenshots/
│   ├── 01-topology.png
│   ├── 02-vlan-summary.png
│   ├── 03-vlan-interface-details.png
│   ├── 04-router-interfaces.png
│   ├── 05-pc1-ipconfig.png
│   ├── 06-pc2-ipconfig.png
│   ├── 07-pc2-cmd-ipconfig.png
│   ├── 08-ping-192.168.20.1-20.2.png
│   ├── 09-ping-192.168.10.1.png
│   ├── 10-acl-output.png
│   └── 11-ping-failure-success.png
├── writeups/
│   ├── 01_physical-topology.md
│   ├── 02_vlan-setup.md
│   ├── 03_router-config.md
│   ├── 04_dhcp-config.md
│   ├── 05_acl-config.md
│   ├── final-lab-review.md
│   └── lab-overview.md
└── lab/
    └── acl-vlan-lab.pkt
📝 Lab Summary
Step 1 — Physical Topology
Created the base network in Packet Tracer:

Router connected to switch on G0/0 → F0/1

PC1 on F0/2

PC2 on F0/3

This provided the foundation for VLAN segmentation and routing.

Step 2 — VLAN Configuration
On the switch:

Created VLAN 10 (HOME)

Created VLAN 20 (LAB)

Assigned access ports:

F0/2 → VLAN 10

F0/3 → VLAN 20

Configured F0/1 as a trunk to the router

Step 3 — Router‑on‑a‑Stick
On the router:

Created subinterfaces:

G0/0.10 → VLAN 10

G0/0.20 → VLAN 20

Assigned gateway IPs for each VLAN

Enabled 802.1Q encapsulation

This allowed inter‑VLAN routing.

Step 4 — DHCP Configuration
Configured DHCP pools:

HOME → 192.168.10.0/24

LAB → 192.168.20.0/24

Excluded gateway addresses

Both PCs successfully received IP addresses and could ping their gateways.

Step 5 — ACL Implementation
Created an ACL to block:

VLAN 20 → VLAN 10 (initiated traffic)

Applied inbound on the VLAN 20 subinterface.
Testing confirmed:

VLAN 20 cannot reach VLAN 10

VLAN 10 can reach VLAN 20

📸 Screenshots
All verification screenshots are included in the screenshots/ folder:

VLAN summaries

Interface configs

IP addressing

Ping tests

ACL results

These provide visual proof of correct configuration and functionality.

🧪 Packet Tracer File
The full lab can be opened in Cisco Packet Tracer:

Code
lab/acl-vlan-lab.pkt
Use this file to explore the topology, configs, and ACL behavior interactively.

🎯 Skills Demonstrated
VLAN creation and segmentation

Trunking and 802.1Q encapsulation

Router‑on‑a‑Stick inter‑VLAN routing

DHCP configuration on a router

ACL creation and traffic filtering

Network troubleshooting and verification

Professional documentation and repo organization

👤 Author
Joshua Epstein  
GitHub: jepstein2233 (github.com in Bing)
