# DAY 1 — Homelab Segmented Network  
**Proxmox + pfSense + Splunk**

## 🧭 Introduction

This homelab started as a simple rebuild, but quickly evolved into a hands-on environment for practicing **real-world network segmentation, firewall enforcement, and centralized logging**.

Instead of placing everything into a flat network, the lab is intentionally segmented based on system roles — **servers, users, and security tools** — with strict control over **who can talk to whom**. Firewalls are not treated as decorative components; every rule exists for a clear and deliberate purpose.

At the same time, visibility is a priority. Logs from multiple network segments are forwarded into a central location, allowing traffic inspection, anomaly detection, and event analysis — similar to workflows in a real **SOC environment**.

The result is a lab that doesn’t just *work*, but **behaves like a production network** — a safe place to test security ideas, intentionally break things, and sharpen detection and investigation skills.

---

## 🧩 Lab Structure Overview

This project is broken down into **5 phases**, each building on the previous one.

---

# ⭐ Phase 1 — Build the Lab Foundation

Phase 1 focuses on building a **clean, stable, and properly segmented foundation**.

Before adding dashboards, detections, or advanced security tooling, the priority is to ensure that the core infrastructure behaves correctly. Everything in later phases depends on this layer, so the emphasis here is on **structure and correctness**, not complexity.

---

## ✅ Phase 1.1 — Homelab Deployment Completed

In this phase, the **core lab infrastructure** is fully deployed and verified.

### 🔹 Proxmox Network Bridges
- Separate virtual bridges are created for:
  - WAN
  - LAN 1
  - LAN 2
  - LAN 3
- This enforces **traffic separation at the hypervisor level**, preventing accidental cross-network access.

---

### 🔹 pfSense Firewall
- A single **pfSense VM** is configured with multiple interfaces.
- Acts as the **central router and firewall** for all networks.
- All inter-network communication is controlled through pfSense policies.

---

### 🔹 Segmented LAN Environments
Each LAN serves a specific purpose:
- **Linux systems** for testing and services
- **Windows Server and Windows client** for enterprise-style scenarios
- **Dedicated monitoring network** for security tools

---

### 🔹 Splunk Server
- A standalone **Splunk instance** is deployed in its own isolated segment.
- Functions as the **centralized log collector** for the entire lab.

---

### 🔹 Firewall Segmentation Rules
- **Default deny** between networks
- Only explicitly required traffic is allowed  
  - Example: log forwarding from internal networks to Splunk

This ensures **clear trust boundaries** and realistic security behavior.

---

## 🟢 Phase 1 Result

By the end of Phase 1:
- The lab is fully deployed
- Network segments are properly isolated
- Firewall rules are enforced intentionally
- Centralized logging is ready for use

The environment is now **stable, segmented, and prepared for monitoring and security testing** in later phases.
