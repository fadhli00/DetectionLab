## 🔐 Part 3 — Security & Centralized Logging

Screenshot Checklist (Quick Reference)

📸 pfSense firewall rules (blocking & allow-to-Splunk)
📸 pfSense interface rules per LAN
📸 Splunk listening port configuration
📸 Splunk receiving logs from LAN1 & LAN2

This phase focuses on enforcing **network security controls** and establishing **centralized visibility** across the entire lab.  
Rather than allowing open communication between systems, the environment is intentionally locked down and monitored, reflecting real-world security practices.

Security is enforced through strict firewall segmentation, while visibility is achieved by forwarding logs from all network segments into a centralized Splunk server.

---

### 🔥 Network Segmentation & Firewall Strategy

All internal networks are isolated by default.  
Inter-LAN communication is denied unless explicitly required and justified.

The segmentation strategy follows these principles:

- Each LAN represents a separate security zone
- No trust relationship exists between LANs
- All access is controlled through explicit pfSense firewall rules
- Internet access is allowed where necessary
- Logging traffic is treated as a special, tightly controlled exception

**Segmentation Rules Overview:**

- ❌ LAN1 ↔ LAN2 — Blocked
- ❌ LAN1 ↔ LAN3 — Blocked
- ❌ LAN2 ↔ LAN3 — Blocked
- ✅ LAN1 → Splunk (192.168.4.10)
- ✅ LAN2 → Splunk (192.168.4.10)
- ✅ LAN3 → Splunk (local logging)

> 📸 **Screenshot Required:**  
> - pfSense firewall rules showing inter-LAN blocking  
> - pfSense rule allowing traffic to Splunk  

---

### 📊 Centralized Logging Architecture

To maintain visibility across isolated segments, all systems forward logs to a centralized Splunk server located in **LAN 3**.

Splunk acts as the central point for:

- Log ingestion
- Event correlation
- Detection and alerting (future phase)
- Incident investigation

This design ensures that even though systems are isolated, **security visibility remains centralized**.

---

### 🔄 Log Flow Overview

The logging flow is designed to be simple, consistent, and controlled:

- **LAN 1 (Linux systems)**  
  Logs are forwarded via syslog or Splunk Universal Forwarder to Splunk.

- **LAN 2 (Windows systems)**  
  Windows event logs are forwarded to Splunk using the Universal Forwarder.

- **LAN 3 (Splunk server)**  
  Receives logs locally and from other LANs.

All logging traffic is explicitly permitted through the firewall and restricted to required ports only.

> 📸 **Screenshot Required:**  
> - Splunk input configuration (listening port enabled)  
> - Splunk showing incoming events from multiple hosts  

---

### 🔍 Security Visibility & Monitoring

Centralized logging provides the ability to:

- Monitor traffic and system activity across all segments
- Identify suspicious behavior
- Validate firewall effectiveness
- Correlate events during investigations

This phase lays the foundation for more advanced capabilities such as detection logic, alerts, and dashboards introduced in later phases.

---

### 🧠 Security Design Philosophy

- **Deny by default**
- **Allow only what is required**
- **Log everything that matters**
- **Document the intent behind every rule**

This approach ensures the lab remains secure, observable, and suitable for continuous testing and learning.

---
