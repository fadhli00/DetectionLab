# 🔐 Proxmox Homelab  
## Homelab — Segmented Network & Security Lab

**Technology Stack:**  
🧱 Proxmox • 🔥 pfSense • 📊 Splunk  

A hands-on security-focused homelab designed to simulate a **segmented enterprise network** with centralized logging, detection, and incident investigation capabilities.

---

## 📖 Introduction

This homelab started as a simple rebuild, but quickly evolved into a hands-on environment for practicing **real network segmentation, firewall control, and centralized logging** in a setup that closely resembles a production network.

Instead of placing all systems into a single flat network, this lab is intentionally designed with **clear separation between systems based on their roles**—such as servers, user machines, and security tools. Each network segment exists for a specific purpose, and all communication between segments is explicitly controlled.  
Firewalls are not just present for formality — **every rule exists for a reason**.

At the same time, visibility is treated as a core requirement. Logs from multiple isolated segments flow into a centralized platform, allowing traffic visibility, anomaly detection, and event analysis similar to a real **Security Operations Center (SOC)**.

The result is a lab that doesn’t just *work*, but **behaves like a real environment**—one that can be safely broken, tested, and analyzed to sharpen detection and investigation skills.

---

## 🧭 Project Scope

This homelab focuses on:

- Network segmentation and isolation
- Firewall rule design and traffic control
- Centralized logging and visibility
- Detection, alerting, and investigation workflows
- Clear documentation and reproducibility

Advanced features are introduced progressively across project phases.

---

## 🧩 Project Phases

Each phase is documented separately for clarity and modular learning:

## 🧩 Project Phases

Each part of this project is documented separately to keep the structure clear, focused, and easy to follow.

🔹 **[Part 1 — Network Design & Topology](phase-1/README.md)**  
  High-level network architecture, segmentation design, and topology overview.

🔹 **[Part 2 — Gather Materials](part-2/README.md)**  
  Capturing network diagrams, screenshots, and technical notes before formal documentation.

🔹 **[Part 3 — Security & Centralized Logging](part-3/README.md)**  
  Firewall segmentation rules, log forwarding, and centralized visibility using Splunk.

🔹 **[Part 4 — Outcomes & Next Steps](part-4/README.md)**  
  Project results, lessons learned, challenges encountered, and future enhancements.

---

## 🎯 Objectives

- Build a **multi-LAN segmented network** using a single firewall
- Enforce **strict inter-network isolation**
- Deploy Linux and Windows systems across isolated segments
- Centralize logs using **Splunk**
- Practice **realistic SOC-style detection and investigation**
- Create a professional, portfolio-ready documentation

---

## 🧪 Lab Environment (High-Level)

| Component        | Purpose |
|------------------|--------|
| Proxmox          | Virtualization platform |
| pfSense          | Central firewall & routing |
| Ubuntu Servers   | Linux workloads & testing |
| Windows Server   | Enterprise-style services |
| Windows Client   | User endpoint simulation |
| Splunk           | Centralized logging & analysis |

---

## 🚀 Why This Lab?

This project is built to bridge the gap between theory and practice by providing:

- Realistic network behavior
- Security-first design
- Safe environment for experimentation
- Hands-on SOC-style workflows

---

## 📌 Status

🟢 **Active / Ongoing**  
Future enhancements include IDS/IPS, automation, and advanced detection logic.

---

