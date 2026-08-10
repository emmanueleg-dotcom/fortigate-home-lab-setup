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

## 🔍 Troubleshooting & Key Learnings

During the deployment process, a few initial challenges were encountered and successfully resolved:

1. **FortiCloud Support Contract Barrier:**
   - **Issue:** Unable to download standard firmware images due to a missing paid support contract requirement on the main portal.
   - **Resolution:** Navigated to the **VM Images** section and selected the correct `.ovf.zip` package (`FortiGate-VM64`) for VMware ESXi evaluation.

2. **CLI Password Security Policy:**
   - **Issue:** Initial password change failed during first boot via CLI.
   - **Resolution:** Identified FortiOS 7.6 strict password enforcement requiring at least 12 characters, including uppercase, lowercase, digits, and special symbols.

3. **Management Interface Connectivity & License Activation:**
   - **Issue:** `port1` initially retained a `0.0.0.0` IP address under DHCP.
   - **Resolution:** Configured network interface settings manually via CLI to obtain a valid local management IP, enabled HTTPS/SSH access, and registered the instance using a **FortiCloud Evaluation License**.
  
## 📸 Lab Screenshots

- **FortiGate Dashboard (GUI):**
  ![FortiGate Dashboard](<img width="1906" height="910" alt="Screenshot 2026-08-10 173548" src="https://github.com/user-attachments/assets/007792c7-ff5c-4f0e-8dff-fab2af138519" />)

- **CLI Initial Setup:**
  ![FortiGate CLI](<img width="957" height="1018" alt="Screenshot 2026-08-10 162952" src="https://github.com/user-attachments/assets/d37be50f-9fb3-4c9e-bbc9-7a0e34ae9204" />)

