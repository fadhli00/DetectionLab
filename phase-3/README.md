## 🔐 Part 4 — Security & Centralized Logging

This phase focuses on enforcing **strict network segmentation** and establishing **centralized visibility** across the entire lab.  
The environment is designed with a **deny-by-default** mindset, where every allowed connection is intentional, documented, and logged.

---

## 🔥 Firewall Segmentation Rules

pfSense acts as the single enforcement point for all traffic entering or leaving each network segment.  
By default, **no LAN is allowed to communicate with another LAN**.

### Segmentation Policy Summary

| Source | Destination | Action | Purpose |
|------|-------------|--------|--------|
| LAN1 | LAN2 | Block | Prevent lateral movement |
| LAN1 | LAN3 | Block | Enforce isolation |
| LAN2 | LAN1 | Block | Prevent lateral movement |
| LAN2 | LAN3 | Block | Enforce isolation |
| LAN3 | LAN1 | Block | Enforce isolation |
| LAN3 | LAN2 | Block | Enforce isolation |
| LAN1 | Internet | Allow | Normal outbound access |
| LAN2 | Internet | Allow | Normal outbound access |
| LAN3 | Internet | Allow | Updates & services |

> 📸 **Screenshot Required:**  
> - pfSense firewall rules showing LAN-to-LAN blocking rules  
> - Rule order clearly visible  

---

### 🔓 Logging Exception Rules (Explicit Allow)

Logging traffic is the **only permitted inter-LAN communication**.

| Source | Destination | Port | Action | Purpose |
|------|-------------|------|--------|--------|
| LAN1 | 192.168.4.10 | 9997 | Allow | Send logs to Splunk |
| LAN2 | 192.168.4.10 | 9997 | Allow | Send logs to Splunk |
| LAN3 | Local | N/A | Allow | Local log processing |

Only the required destination and port are permitted.  
No other services are exposed across network boundaries.

> 📸 **Screenshot Required:**  
> - pfSense rule allowing LAN1 → Splunk  
> - pfSense rule allowing LAN2 → Splunk  

---

## 📊 Centralized Logging Architecture

All systems forward logs to a **dedicated Splunk server located in LAN 3 (192.168.4.10)**.  
This allows visibility across isolated environments without breaking segmentation.

Splunk is responsible for:

- Log ingestion
- Indexing and storage
- Event correlation
- Detection and alerting (future phase)

---

## 🔄 Log Flow Design

The log flow is intentionally simple and controlled:

### Linux Systems (LAN 1)
- System and application logs forwarded using syslog or Splunk Universal Forwarder
- Destination: Splunk server (192.168.4.10:9997)

### Windows Systems (LAN 2)
- Windows Event Logs forwarded using Splunk Universal Forwarder
- Destination: Splunk server (192.168.4.10:9997)

### Splunk Server (LAN 3)
- Receives logs locally
- Receives logs from LAN 1 and LAN 2
- Acts as the central analysis point

> 📸 **Screenshot Required:**  
> - Splunk input configuration (port 9997 enabled)  
> - Splunk showing events from multiple hosts  

---

## 🔍 Security Visibility & Monitoring

With centralized logging in place, the lab enables:

- Validation of firewall rule effectiveness
- Detection of unexpected traffic patterns
- Cross-host event correlation
- Investigation of simulated security incidents

This phase establishes the groundwork for advanced detection and SOC-style workflows in later phases.

---

## 🧠 Security Design Principles

- Deny all inter-LAN traffic by default
- Allow only specific, justified flows
- Log and monitor all critical activity
- Document the intent behind every firewall rule

This ensures the environment remains secure, observable, and easy to reason about.

---
