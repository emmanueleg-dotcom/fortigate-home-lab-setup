# 🛡️ FortiGate Next-Generation Firewall (FortiOS 7.6) Lab Setup

## 📌 Overview
This project documents the installation, initial configuration, and security setup of a **FortiGate VM (FortiOS 7.6)** running on VMware Workstation for hands-on network security practice.

## 📐 Network & Lab Architecture
- **Hypervisor:** VMware Workstation
- **Firewall:** FortiGate VM64 (FortiOS 7.6)
- **Management Access:** HTTPS / SSH via `port1` (Management Subnet)
- **License Type:** FortiCloud Evaluation License

## 🚀 Step-by-Step Implementation

### 1. VM Import & Network Adapter Setup
1. Downloaded the FortiGate VM image (`.ovf`) from the Fortinet Support Portal.
2. Imported the template into VMware Workstation.
3. Configured Network Adapters (`port1` set to DHCP/Management Subnet).

### 2. Initial CLI Configuration & Security Hardening
Configured initial management interface and enforced strong password policies via CLI:

```text
config system interface
    edit "port1"
        set mode dhcp
        set allowaccess ping https ssh http
    end
```

### 3. FortiCloud Integration & Evaluation License
Linked the VM instance with FortiCloud for full feature evaluation.

Verified system status, interface assignments, and admin dashboard controls.

Created as part of my continuous learning in Network Security and Fortinet Ecosystem.
