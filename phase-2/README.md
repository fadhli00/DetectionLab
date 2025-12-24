## 🛠️ Part 3 — Build Process

This section documents the **implementation process** of the homelab, focusing on how the environment was built step by step.  
The goal is not to provide exhaustive configuration commands, but to clearly explain **what was built, in what order, and why**.

The build process is structured to ensure that the network foundation is stable before adding systems, security controls, and logging capabilities.

---

### Phase 1 — Proxmox Network Foundation

The lab begins with the setup of the Proxmox host and its network configuration.

Key actions:
- Created multiple Linux bridges to represent each network segment
- Mapped each bridge to a dedicated LAN or WAN
- Ensured network persistence across reboots
- Verified internet connectivity through the WAN bridge

This establishes a clean and modular virtualization layer where network segmentation starts at the hypervisor level.

---

### Phase 2 — pfSense Deployment

pfSense is deployed as a virtual machine and configured as the **central firewall and router**.

Key actions:
- Assigned multiple network interfaces to pfSense
- Mapped each interface to the appropriate Proxmox bridge
- Configured IP addressing and gateways for each LAN
- Enabled DHCP where appropriate

At this stage, pfSense becomes the single control point for all routing and security enforcement.

---

### Phase 3 — Internal System Deployment

With the network and firewall in place, systems are deployed into their respective segments.

Key actions:
- Deployed Ubuntu systems in LAN 1 for baseline Linux testing
- Deployed Windows Server and Windows client systems in LAN 2
- Deployed a dedicated Splunk server in LAN 3
- Verified connectivity to gateways and outbound internet access

Each system is connected only to its intended network segment, maintaining isolation by design.

---

### Phase 4 — Initial Validation

Before moving into security controls and logging, basic validation is performed.

Validation checks:
- Gateway reachability from each LAN
- Internet access from internal systems
- Correct IP addressing and routing behavior
- Isolation between LANs prior to rule tuning

This ensures the environment is stable and ready for security-focused configuration.

---

### Build Philosophy

- Build **from the network outward**
- Enforce segmentation early
- Validate each layer before moving on
- Keep configurations documented and reproducible

This approach mirrors how infrastructure is built and validated in real production environments.

---
