# Infrastructure Notes

## Resource Names
- Resource Group: rg-soc-lab
- Virtual Network: vnet-soc
- Subnet: subnet-soc

## Naming Convention
All resources follow the pattern `<type>-<component>-<env>`  
Example: `vm-sysmon-lab`, `law-soc`, `rg-soc-lab`

## Next Steps
- Deploy Log Analytics Workspace
- Enable Microsoft Sentinel
- Configure diagnostic settings

## Azure Networking Setup
- Resource Group: rg-soc-lab (Central India)
- Virtual Network: vnet-soc (10.0.0.0/16)
- Subnet: subnet-soc (10.0.1.0/24)
- Status: Deployed successfully via Azure Portal

## Log Analytics Workspace & Microsoft Sentinel

### Log Analytics Workspace
- Name: law-soc
- Region: Central India
- Resource Group: rg-soc-lab
- Purpose: Central log storage and analytics query engine for SOC data.

### Microsoft Sentinel
- Connected Workspace: law-soc
- Function: SIEM + SOAR platform for detection, investigation & automation.
- Status: Deployed and verified.

### Visuals
![LAW Overview](./screenshots/law-soc-overview.png)
![Sentinel Overview](./screenshots/sentinel-overview.png)
