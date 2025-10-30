# Azure Infrastructure Setup

## Overview
This section documents the foundational Azure environment for the Cloud SOC build.

## Resource Group
- **Name:** rg-soc-lab  
- **Region:** Central India  
- **Purpose:** Logical container for all SOC lab components  

## Virtual Network
- **Name:** vnet-soc  
- **Address Space:** 10.0.0.0/16  
- **Subnet:** subnet-soc (10.0.1.0/24)

## Visual Proof
### Resource Group
![Resource Group Overview](./screenshots/resource-group-overview.png)

### Virtual Network
![Virtual Network Overview](./screenshots/vnet-overview.png)

### Subnet
![Subnet SOC](./screenshots/subnet-soc.png)

## Status
✅ Successfully created via Azure Portal and verified.
