## Preserving the Lab in a Clean State

Once the lab was fully deployed and running as intended, I resisted the urge to immediately begin writing documentation or pushing content to GitHub. Instead, I treated this phase as a deliberate pause — a moment to capture the environment exactly as it existed before changes, tweaks, and experiments inevitably began.

This phase became the **raw material collection stage**. The goal wasn’t polish or presentation, but preservation. I wanted to lock in the current state of the lab while everything was still fresh, accurate, and stable, knowing these references would later shape clean diagrams, explanations, and structured write-ups.

---

## ✅ Capturing the Lab in Its “Clean” State

While the environment was still stable, I began taking screenshots to document key design and security decisions. These visuals serve as evidence of how the lab was built and how segmentation is enforced.

### Proxmox Configuration

- Proxmox bridge configuration

<p align="center">
  <img src="images/networkbridge.png" alt="Proxmox Network Bridge Configuration" width="800">
</p>

---

### pfSense Interface Assignments

- WAN Interface

<p align="center">
  <img src="images/WAN.png" alt="pfSense WAN Interface" width="800">
</p>

- LAN Interface

<p align="center">
  <img src="images/LAN.png" alt="pfSense LAN Interface" width="800">
</p>

- OPT1 Interface

<p align="center">
  <img src="images/OPT1.png" alt="pfSense OPT1 Interface" width="800">
</p>

- OPT2 Interface

<p align="center">
  <img src="images/OPT2.png" alt="pfSense OPT2 Interface" width="800">
</p>

---

### Virtual Machines Across Segments

#### LAN 1 – Linux Systems

<p align="center">
  <img src="images/LAN.png" alt="LAN 1 Linux Systems" width="800">
</p>

---

#### LAN 2 – Windows Environment

- Windows Server 2016  
- Windows 10 Client  

<p align="center">
  <img src="images/LAN 2.png" alt="LAN 2 Windows Environment" width="800">
</p>

---

#### LAN 3 – Splunk Server

<p align="center">
  <img src="images/LAN 3.png" alt="LAN 3 Splunk Server" width="800">
</p>

---

### Splunk Logging & Forwarders

- Splunk actively receiving logs from multiple isolated segments
- Data retention threshold set to **2 days**
  - Suitable for a homelab
  - **Not recommended for enterprise environments**

#### Linux Server Splunk Forwarder

<p align="center">
  <img src="images/server splunk forwarder.png" alt="Linux Splunk Forwarder" width="800">
</p>

#### Windows Splunk Forwarder

<p align="center">
  <img src="images/windows splunk forwarder.png" alt="Windows Splunk Forwarder" width="800">
</p>

#### Splunk Web UI

<p align="center">
  <img src="images/splunk ui.png" alt="Splunk Web Interface" width="800">
</p>

---

These screenshots ensure that critical architectural and security decisions are visually documented before any future changes are introduced.

---

## ✅ Writing Notes Before They’re Forgotten

Alongside screenshots, I kept simple technical notes — nothing fancy, just accurate. The focus was capturing details while they were still clear, not making them look polished.

### Network Flow

- WAN → Modem/Router → pfSense → Proxmox → Virtual Machines

---

### Segmentation Policy

- LAN1, LAN2, and LAN3 are fully isolated by default
- Explicitly allowed traffic:
  - LAN1 → Splunk (`192.168.4.10`)
  - LAN2 → Splunk (`192.168.4.10`)
  - LAN3 → Splunk (local)
- No direct LAN-to-LAN communication permitted

---

### Additional Notes

- Virtual machine names and assigned roles
- Firewall rule intent and reasoning
- Log flow direction across the environment
