
---

## ✅ Capturing the Lab in Its “Clean” State

While the environment was still stable, I began taking screenshots to document key design and security decisions. These visuals serve as evidence of how the lab was built and how segmentation is enforced.

### Captured Screenshots

#### Proxmox
- **Proxmox bridge configuration**
<p align="center">
  <img src="images/networkbridge.png" alt="Homelab Network Topology" width="800">
</p>

#### pfSense
- **Interface assignments**
- **Firewall rules segmentation**

**WAN**
<p align="center">
  <img src="images/WAN.png" alt="Homelab Network Topology" width="800">
</p>

**LAN1**
<p align="center">
  <img src="images/LAN.png" alt="Homelab Network Topology" width="800">
</p>

**LAN2**
<p align="center">
  <img src="images/OPT1.png" alt="Homelab Network Topology" width="800">
</p>

**LAN3**
<p align="center">
  <img src="images/OPT2.png" alt="Homelab Network Topology" width="800">
</p>

---

### Virtual Machines Deployed Across All Segments

**LAN 1: Linux systems**
<p align="center">
  <img src="images/UBUNTU.png" alt="Homelab Network Topology" width="800">
</p>

**LAN 2: Windows Server and Windows client**

- Windows Server 2016: windows server 
<p align="center">
  <img src="images/windows server.png" alt="Homelab Network Topology" width="800">
</p>


- Windows 10: WINDOWS  
<p align="center">
  <img src="images/WINDOWS.png" alt="Homelab Network Topology" width="800">
</p>


**LAN 3: Splunk server**
<p align="center">
  <img src="images/splunk status.png" alt="Homelab Network Topology" width="800">
</p>

---

### Splunk Logging

- Splunk actively receiving logs from multiple isolated segments  
- I set the treshold for data rentention of splunk keeping the logs for two days. For this homelab that threshold Is good enough for my environment. But for the enterprise that is not a good practise.  

**Server Splunk Forwarder**
<p align="center">
  <img src="images/server splunk forwarder.png" alt="Homelab Network Topology" width="800">
</p>

**Windows Splunk Forwarder**
<p align="center">
  <img src="images/windows splunk forwarder.png " alt="Homelab Network Topology" width="800">
</p>

**Splunk UI**
<p align="center">
  <img src="images/splunk ui.png" alt="Homelab Network Topology" width="800">
</p>

These screenshots ensure that critical architectural and security choices are visually documented before any future changes are introduced.

---

## ✅ Writing Notes Before They’re Forgotten

Alongside screenshots, I kept simple technical notes nothing fancy, just accurate. The focus here was capturing details while they were still clear in my head, not making them look good.

### Network Flow
- WAN → Modem/Router → pfSense → Proxmox → Virtual Machines

### Segmentation Policy
- LAN1, LAN2, and LAN3 are fully isolated by default
- Explicitly allowed traffic:
  - LAN1 → Splunk (192.168.4.10)
  - LAN2 → Splunk (192.168.4.10)
  - LAN3 → Splunk (local)
- No direct LAN-to-LAN communication permitted

### Additional Notes
- Virtual machine names and assigned roles
- Firewall rule intent and reasoning
- Log flow direction across the environment

---

⬅️ **Previous:** [Part 1 — Network Design & Topology](../Part-1/README.md)  
➡️ **Next:** [Part 3 — Security Controls & Log Flow](../Part-3/README.md)

