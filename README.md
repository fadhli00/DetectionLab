# Proxmox Homelab — Phase 1

## 🔰 Objective
Setup Proxmox host and basic VM layout.

## 🖥️ Hardware
- CPU: Ryzen 5 5600U
- RAM: 7 GB
- Storage: 512 GB NVMe

## 🧱 VM List
| VM ID | OS | RAM | Purpose |
|-----|----|-----|--------|
| 101 | Ubuntu | 1 GB | Utility |
| 102 | pfSense | 1 GB | Firewall |
| 103 | Windows Server | 2 GB | Lab |
| 104 | Windows 10 | 1.5 GB | Client |

## ⚠️ Issues Found
- Host RAM bottleneck
- Swap usage high (3–4 GB)

## ✅ Phase 1 Result
All VMs running, but performance not stable due to RAM limit.

## 📌 Next Plan (Phase 2)
- Optimize RAM allocation
- Enable ballooning
- Consider RAM upgrade
