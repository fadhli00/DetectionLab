## ⭐ Phase 2 — Gather Materials (Before Writing Anything)

With the lab fully deployed and operational, this phase focuses on **capturing what already exists**.  
Rather than rushing into documentation or publishing to GitHub, the priority here is to collect visuals and technical notes while the environment is still fresh, accurate, and unchanged.

This phase serves as the **raw material collection stage**—everything gathered here will later be refined into clean documentation, diagrams, and structured write-ups.

---

### ✅ Capture Key Screenshots

Screenshots are taken while the environment is still clean and stable.  
These visuals help preserve the exact state of the lab and will later support explanations throughout the documentation.

Captured screenshots include:

- Proxmox bridge configuration
- pfSense interface assignments
- Firewall rules demonstrating network segmentation:
  - WAN
  - LAN
  - OPT1
  - OPT2
  - OPT3
- Virtual machines across all segments:
  - LAN 1 — Linux systems
  - LAN 2 — Windows Server and Windows client
  - LAN 3 — Splunk server
- VM list showing network placement
- Splunk successfully receiving logs from multiple segments

These screenshots ensure that key design and security decisions are visually documented.

---

### ✅ Collect Technical Notes

Basic technical details are gathered in a simple text file or Word document.  
The focus here is **accuracy, not polish**.

Collected notes include:

#### Network Flow
- WAN → Modem/Router → pfSense → Proxmox → Virtual Machines

#### Proxmox Bridges
- `vmbr0` — WAN  
- `vmbr1` — LAN 1  
- `vmbr2` — LAN 2  
- `vmbr3` — LAN 3  

#### pfSense Interfaces
- WAN — DHCP from ISP  
- OPT1 — 192.168.2.1  
- OPT2 — 192.168.3.1  
- OPT3 — 192.168.4.1  

#### Network Segments & VMs
- **LAN 1:** 192.168.2.0/24 — Ubuntu VM  
- **LAN 2:** 192.168.3.0/24 — Windows Server + Windows 10  
- **LAN 3:** 192.168.4.0/24 — Splunk Server (192.168.4.10)  

#### Segmentation Policy
- LAN1, LAN2, and LAN3 are **fully isolated**
- Allowed traffic:
  - LAN1 → Splunk (192.168.4.10)
  - LAN2 → Splunk (192.168.4.10)
  - LAN3 → Splunk (local)
- No direct LAN-to-LAN communication permitted

#### Additional Notes
- Virtual machine names and roles
- Firewall rule intent and reasoning
- Log flow direction across the environment

These notes do not need to be perfect.  
They simply need to exist, as they form the **foundation for future documentation, README sections, and GitHub content**.

---
