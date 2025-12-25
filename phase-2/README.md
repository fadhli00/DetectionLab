## ⭐ Phase 2 — Gather Materials (Before Writing Anything)

Once the lab was fully deployed and running the way I intended, I resisted the urge to immediately start writing documentation or pushing content to GitHub. Instead, I treated this phase as a pause—a moment to capture the environment exactly as it existed before changes, tweaks, and experiments inevitably began.

This phase became the **raw material collection stage**. The goal wasn’t polish or presentation, but preservation. I wanted to lock in the current state of the lab while everything was still fresh, accurate, and stable, knowing that these references would later shape clean diagrams, explanations, and structured write-ups.

---

### ✅ Capturing the Lab in Its “Clean” State

While the environment was still stable, I began taking screenshots to document key design and security decisions. These visuals serve as evidence of how the lab was built and how segmentation is enforced.

Captured screenshots include:

- Proxmox bridge configuration
- pfSense interface assignments
- Firewall rules demonstrating segmentation across:
  - WAN
  - LAN
  - OPT1
  - OPT2
  - OPT3
- Virtual machines deployed across all segments:
  - **LAN 1:** Linux systems
  - **LAN 2:** Windows Server and Windows client
  - **LAN 3:** Splunk server
- VM inventory showing network placement
- Splunk actively receiving logs from multiple isolated segments

These screenshots ensure that critical architectural and security choices are visually documented before any future changes are introduced.

---

### ✅ Writing Notes Before They’re Forgotten

Alongside screenshots, I kept simple technical notes—nothing fancy, just accurate. The focus here was capturing details while they were still clear in my head, not making them look good.

The notes cover:

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
- LAN1, LAN2, and LAN3 are **fully isolated by default**
- Explicitly allowed traffic:
  - LAN1 → Splunk (192.168.4.10)
  - LAN2 → Splunk (192.168.4.10)
  - LAN3 → Splunk (local)
- No direct LAN-to-LAN communication permitted

#### Additional Notes
- Virtual machine names and assigned roles
- Firewall rule intent and reasoning
- Log flow direction across the environment

These notes don’t need to be perfect—they just need to exist. They form the **foundation** for future documentation, README sections, diagrams, and GitHub content, making sure nothing important gets lost as the lab continues to evolve.

---
