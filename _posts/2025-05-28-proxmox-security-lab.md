---
layout: post
title: "Building a security lab with Proxmox VE"
date: 2025-05-28
tags: [homelab, infrastructure]
excerpt: "Converted my old gaming rig into a proper virtualization host. Proxmox VE made more sense than running everything in VirtualBox on my daily driver."
---

Converted my old gaming rig into a proper virtualization host. Proxmox VE made more sense than running everything in VirtualBox on my daily driver.

Current setup runs Kali Linux, Windows 10, Server 2019, and various vulnerable VMs. Network segmentation keeps everything isolated while allowing controlled communication between segments.

The real game-changer is being able to snapshot states before running exploits, then roll back for clean retesting.

### Hardware & Setup

**Base system:**
- Intel i7-8700K (plenty of cores for multiple VMs)
- 32GB RAM (16GB allocated to VMs, rest for host)
- 1TB NVMe for VM storage + 2TB HDD for backups
- Dedicated NIC for management interface

**Network design:**
- Management VLAN (192.168.10.x)
- Attack range (10.0.1.x) - Isolated from production
- Target range (10.0.2.x) - Vulnerable systems
- DMZ (10.0.3.x) - Services and honeypots

### Key Benefits Over Desktop Virtualization

**Performance:** Native Type-1 hypervisor beats VirtualBox/VMware Workstation
**Isolation:** Proper network segmentation prevents accidents
**Snapshots:** Web-based management makes rollbacks effortless
**Remote access:** Can run exploits from anywhere via web console

### Current VM Lineup

- **Kali Linux** - Primary attack platform
- **Windows 10** - Client-side attack testing
- **Server 2019** - AD environment simulation  
- **Metasploitable2** - Classic vulnerable Linux
- **VulnHub VMs** - Rotating through practice machines
- **pfSense** - Network segmentation and traffic analysis

The investment in proper lab infrastructure is paying dividends. Having reliable, isolated environment for testing makes the learning process so much smoother. 