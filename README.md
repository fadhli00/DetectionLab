# 🔐 Proxmox Homelab  
## Homelab — Segmented Network & Security Lab  

**Technology Stack:** 🧱 Proxmox • 🔥 pfSense • 📊 Splunk  

A hands-on, security-first homelab built to **feel like a real enterprise environment**not a flat test network. This lab focuses on segmentation, visibility, and investigation, giving me a safe place to break things, fix them, and actually learn how modern SOC environments behave.

---

## 📖 The Turning Point  

This lab started during a quiet night shift early in my SOC journey. Between SIEM alerts, detections, and constantly changing rules, it felt like there was always more to learn but nowhere safe to experiment.  

That’s when I remembered an old, unused laptop sitting at home. Nothing fancy. Not powerful. Just *good enough*.  

I installed Proxmox directly on bare metal, and what began as a simple setup quickly escalated. As I hit limitations, made mistakes, and redesigned things, the lab turned into a full-blown security playground one that actually resembled a production environment instead of a throwaway setup.

Rather than dumping everything into a single network, I segmented systems by role: servers, user endpoints, and security tools. Every firewall rule had to be justified. Every allowed connection was tested, broken, and refined. Visibility wasn’t optional either logs from isolated networks were centralized for detection, analysis, and investigation.

The result is a lab that doesn’t just *run*, but **behaves like a real environment**one I can safely abuse, monitor, and use to sharpen my SOC detection and incident response skills.

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

Each part of the project is documented separately to keep things clean, modular, and easy to follow:

🔹 **[Part 1 — Network Design & Topology](phase-1/README.md)**  
High-level architecture, segmentation strategy, and topology overview.

🔹 **[Part 2 — Gather Materials](phase-2/README.md)**  
Capturing diagrams, screenshots, and technical notes before formal documentation.

🔹 **[Part 3 — Security & Centralized Logging](phase-3/README.md)**  
Firewall rules, log forwarding, and centralized visibility using Splunk.

🔹 **[Part 4 — Outcomes & Next Steps](phase-4/README.md)**  
Lessons learned, challenges, results, and future improvements.

---

## 🎯 Objectives  

- Build a **multi-LAN segmented network** behind a single firewall  
- Enforce **strict inter-network isolation**  
- Deploy Linux and Windows systems across isolated segments  
- Centralize logs using **Splunk**  
- Practice **realistic SOC-style detection and investigation**  
- Produce clean, portfolio-ready documentation  

---

## 🧪 Lab Environment (High-Level)  

| Component        | Purpose                         |
|------------------|----------------------------------|
| Proxmox          | Virtualization platform           |
| pfSense          | Central firewall & routing        |
| Ubuntu Servers   | Linux workloads & testing         |
| Windows Server   | Enterprise-style services         |
| Windows Client   | User endpoint simulation          |
| Splunk           | Centralized logging & analysis    |

---

## 🚀 Why This Lab?  

This project exists to close the gap between theory and reality by providing:
- Realistic network behavior  
- Security-first design choices  
- A safe space to experiment (and break things)  
- Hands-on SOC-style workflows  

---

## 📌 Status  

🟢 **Active / Ongoing**  

Planned enhancements include IDS/IPS, automation, and more advanced detection logic.
