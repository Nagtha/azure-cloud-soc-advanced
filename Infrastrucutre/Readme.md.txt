# Infrastructure Notes

This section documents the Azure infrastructure setup for the **Azure Cloud SOC Advanced** project.

---

## 🌐 Resource Overview

| Component | Name | Description |
|------------|------|-------------|
| **Resource Group** | rg-soc-lab | SOC resource container |
| **Virtual Network** | vnet-soc (10.0.0.0/16) | Core SOC network |
| **Subnet** | subnet-soc (10.0.1.0/24) | Hosts all VMs and NSG |
| **Region** | Central India | Deployment location |

Naming convention:  
`<type>-<component>-<env>` → Example: `vm-victim-win`, `law-soc`, `rg-soc-lab`

---

## 🧱 Phase 1 — Foundation Setup

- Created **Resource Group (rg-soc-lab)**  
- Created **VNet (vnet-soc)** and **Subnet (subnet-soc)**  
- Established consistent resource naming policy  
- Verified deployment via Azure Portal  

**Screenshots:**  
- `phase1-vnet-overview.png`  
- `phase1-subnet-overview.png`  
- `phase1-resourcegroup-overview.png`

---

## ⚙️ Phase 2 — Virtual Machines & Network Security

### Virtual Machines
- **vm-victim-win** (Windows Server)
- **vm-attacker-linux** (Ubuntu)
- Both connected to `subnet-soc`

### Network Security Group
- **Name:** nsg-soc  
- **Associated with:** subnet-soc  
- **Rules:**

| Priority | Name | Port | Protocol | Source | Destination | Action |
|-----------|------|------|-----------|----------|--------------|---------|
| 100 | allow-rdp-admin | 3389 | TCP | 27.4.143.232/32 | Any | Allow |
| 110 | allow-ssh-admin | 22 | TCP | 27.4.143.232/32 | Any | Allow |
| 120 | allow-vnet-traffic | Any | Any | VirtualNetwork | VirtualNetwork | Allow |

### NSG Flow Logs
- **Version:** 2  
- **Storage Account:** stlogsoc  
- **Retention:** 7 days  
- **Traffic Analytics:** Pending (will connect to LAW in Phase 3)  
- **Log Type:** NSG  

**Screenshots:**  
- `phase2-vm-victim-win.png`  
- `phase2-vm-attacker-linux.png`  
- `phase2-nsg-rules.png`  
- `phase2-flowlogs.png`

---

## 📊 Phase 3 — Log Analytics & Sentinel (Next)

### Planned Configuration
- **Workspace:** law-soc  
- **Region:** Central India  
- **Purpose:** Central log collection and analytics engine  
- **Resource Group:** rg-soc-lab  
- **To be connected:** NSG Flow Logs + VMs + Sysmon  

**Upcoming Integrations**
- Microsoft Sentinel onboarding  
- Diagnostic settings configuration  
- Data connector setup (VM, NSG, Sysmon)

---

## 🧾 Notes
- All storage accounts use **Standard LRS** for cost optimization  
- Traffic logs are retained in **stlogsoc** for 7 days  
- Public inbound ports (RDP/SSH) restricted to admin IP (27.4.143.232)

---

📸 **All screenshots are stored in:**  
`Infrastructure/Screenshots/`

- `phase1-vnet-overview.png`
- `phase1-subnet-overview.png`
- `phase2-nsg-rules.png`
- `phase2-vm-victim-win.png`
- `phase2-flowlogs.png`
- `phase3-law-overview.png`

---

🧠 *This documentation will expand as more SOC telemetry and automation components are deployed.*
