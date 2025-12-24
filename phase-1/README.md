## 🧩 Part 1 — Network Design & Topology

This homelab is designed around a **segmented network architecture** where each network segment is isolated by default and controlled through a central firewall. The goal is to mimic how networks are structured in real enterprise environments, rather than using a single flat network.

At the core of the design is **pfSense**, acting as the central gateway responsible for routing, firewall enforcement, and traffic control between all network segments.

---

### 🔐 Network Segmentation Overview

The network is divided into multiple logical segments, each serving a specific role:

| Segment | Subnet | Purpose |
|-------|--------|--------|
| WAN | Provided by ISP | Internet uplink |
| LAN 1 | 192.168.2.0/24 | Linux systems and baseline testing |
| LAN 2 | 192.168.3.0/24 | Windows Server and user endpoints |
| LAN 3 | 192.168.4.0/24 | Security tools and logging (Splunk) |

Each LAN is treated as an isolated security zone. By default, **no direct communication between LANs is allowed** unless explicitly permitted by firewall rules.

---

### 🧱 Virtualization & Network Layout

The lab is hosted on **Proxmox**, using Linux bridges to represent each network segment:

| Proxmox Bridge | Connected Network |
|--------------|------------------|
| vmbr0 | WAN |
| vmbr1 | LAN 1 |
| vmbr2 | LAN 2 |
| vmbr3 | LAN 3 |

Virtual machines are connected only to the bridge that corresponds to their intended network segment. This enforces segmentation at both the **hypervisor** and **firewall** layers.

---

### 🔥 pfSense Interface Design

pfSense is deployed with multiple interfaces, one for each network segment:

| Interface | IP Address | Network |
|---------|------------|---------|
| WAN | DHCP | Internet |
| OPT1 | 192.168.2.1 | LAN 1 |
| OPT2 | 192.168.3.1 | LAN 2 |
| OPT3 | 192.168.4.1 | LAN 3 |

pfSense serves as the **default gateway** for all internal networks and is responsible for enforcing security boundaries between them.

---

### 🔄 Traffic Flow Philosophy

- Outbound internet access is allowed from all LANs.
- Inter-LAN traffic is **blocked by default**.
- Exceptions are made only for **centralized logging** and required services.
- All access is controlled through explicit, documented firewall rules.

This design ensures strong isolation while still maintaining operational visibility across the environment.

---

### 🗺️ Topology Diagram

> *(Insert network topology diagram here)*

The diagram visually represents how Proxmox, pfSense, and the segmented LANs interact within the lab environment.

---
