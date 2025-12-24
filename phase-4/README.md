## ✅ Part 5 — Outcomes & Next Steps

This final section summarizes the results of the homelab project, key takeaways from the build, and planned improvements for future iterations.

The lab is considered functional, stable, and suitable for continued security testing and learning.

---

## 🎯 Project Outcomes

The completed homelab successfully achieves its core objectives:

- A fully functional **segmented network architecture** with multiple isolated LANs
- A centralized firewall enforcing **deny-by-default** security policies
- Controlled inter-LAN communication limited strictly to logging traffic
- A centralized Splunk server receiving logs from Linux and Windows systems
- A realistic environment that mirrors **enterprise-style network and security design**

The lab behaves predictably and securely, allowing safe experimentation without compromising isolation.

---

## 🧠 Key Learnings

Through building and operating this environment, the following skills and concepts were reinforced:

- Designing and implementing **network segmentation** from both hypervisor and firewall layers
- Translating security requirements into **clear, enforceable firewall rules**
- Understanding how centralized logging enables visibility across isolated systems
- Appreciating the importance of documentation and diagram-driven design
- Troubleshooting network and logging issues in a structured manner

This project highlighted how visibility and control must be designed together, not added later.

---

## ⚠️ Challenges Encountered

Some of the challenges faced during the project included:

- Managing firewall rule order and rule scope to avoid unintended access
- Verifying that segmentation remained intact while allowing required log traffic
- Ensuring consistent log delivery across different operating systems
- Maintaining clarity while documenting a multi-component environment

Each challenge contributed to a deeper understanding of real-world network and security operations.

---

## 🚀 Next Steps & Future Enhancements

The lab is designed to be expanded incrementally. Planned next steps include:

- **Detection & Alerting**
  - Create Splunk dashboards and alerts
  - Develop basic detection logic for suspicious activity

- **Attack Simulation**
  - Generate benign and malicious traffic to test detections
  - Simulate lateral movement attempts and blocked connections

- **Incident Investigation**
  - Practice SOC-style investigations using correlated logs
  - Build investigation playbooks based on lab scenarios

- **Security Enhancements**
  - Add IDS/IPS (e.g., Suricata)
  - Integrate endpoint telemetry
  - Improve log enrichment and normalization

---

## 📌 Project Status

🟢 **Active and Extensible**

This homelab will continue to evolve as new security concepts and tools are introduced.  
It serves as a long-term learning platform rather than a one-time build.

---
