# Azure Cloud SOC — Advanced
> A hands-on project replicating enterprise-grade SOC deployment in Azure — built for detection, monitoring, and response using Sentinel, Log Analytics, and SOAR.

An end-to-end Azure Security Operations Center (SOC) implementation demonstrating **detection**, **automation**, **MITRE ATT&CK mapping**, **threat intelligence integration**, **endpoint telemetry**, and **DevSecOps practices**.

---

## 🌐 Overview

This project builds a fully functional, cloud-native **Security Operations Center (SOC)** on Microsoft Azure using:

- **Microsoft Sentinel (SIEM)**
- **Azure Log Analytics Workspace**
- **Logic Apps (SOAR)**
- **Sysmon-based endpoint telemetry**
- **Threat Intelligence Feeds (TI Indicators)**
- **MITRE ATT&CK Mapping**
- **Power BI Dashboards for visualization**
- **Infrastructure-as-Code (Terraform/ARM templates)**

---

## 🧩 Architecture Progress

| Phase | Focus | Status |
|--------|--------|--------|
| **Phase 1** | Azure Resource Group & VNet setup | ✅ Completed |
| **Phase 2** | Virtual Machines, NSG Rules & NSG Flow Logs | ✅ Completed |
| **Phase 3** | Log Analytics Workspace & Sentinel Onboarding | 🕓 In Progress |
| **Phase 4** | Sysmon Telemetry & Data Connector Setup | ⏳ Pending |
| **Phase 5** | Threat Intelligence & Automation Rules | ⏳ Pending |

---

## ⚙️ Current Implementation

✅ **Resource Group & Networking**
- Created `rg-soc-lab`, `vnet-soc`, and `subnet-soc`
- Defined consistent naming convention using `<type>-<component>-<env>`

✅ **Virtual Machines**
- **vm-victim-win** — Windows Server (for endpoint telemetry)
- **vm-attacker-linux** — Ubuntu (for threat simulation)

✅ **Network Security**
- Configured **nsg-soc** with controlled inbound rules (RDP, SSH)
- Enabled **NSG Flow Logs v2** with retention to `stlogsoc` storage account

🕓 **Next Step**
- Deploy **Log Analytics Workspace (`law-soc`)**
- Onboard **Microsoft Sentinel**
- Connect NSG Flow Logs for Traffic Analytics and SOC correlation

## 🌟 Repository Highlights

- Fully documented **Azure SOC build** with screenshots and IaC-ready structure  
- Real-world **VM simulation (attacker-victim)** for traffic analysis  
- Flow logs and telemetry streamed into **Log Analytics Workspace**  
- Designed for continuous updates across **five SOC phases**


---

## 🧠 Learning Outcomes

This project demonstrates:
- Building Azure SOC architecture from scratch  
- Configuring telemetry flow from network → analytics → SIEM  
- Implementing incident response automation (SOAR)  
- Mapping alerts to MITRE ATT&CK framework  
- Visualizing SOC metrics in Power BI  

---

## 📂 Repository Structure

azure-cloud-soc-advanced/
│
├── Dashboards/ # Power BI or Sentinel workbooks
├── Documentation/ # Architecture diagrams, notes
├── Infrastructure/ # Azure setup details + screenshots
│ └── Screenshots/
├── Notebooks/ # KQL queries and Jupyter notebooks
├── Playbooks/ # Logic App JSON for automation
├── LICENSE
├── .gitignore
└── README.md

## 🔗 References

- [Microsoft Sentinel Documentation](https://learn.microsoft.com/azure/sentinel/)
- [MITRE ATT&CK Framework](https://attack.mitre.org/)
- [Azure Log Analytics](https://learn.microsoft.com/azure/azure-monitor/logs/)
- [Azure NSG Flow Logs](https://learn.microsoft.com/azure/network-watcher/network-watcher-nsg-flow-logging-overview)

---

📌 *This is an ongoing professional SOC lab build — new modules and configurations will be added progressively.*

