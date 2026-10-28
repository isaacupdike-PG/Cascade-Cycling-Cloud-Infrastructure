# Azure Infrastructure

## Overview

The Cascade Cycling environment uses Microsoft Azure virtual machines to support employee workstations, management access, and security monitoring. The resources are deployed across two Azure regions.

## Virtual Machines

| Virtual Machine | Operating System | Region | Purpose |
|---|---|---|---|
| Employee-VM01 | Windows 11 Enterprise | West US 2 | Employee workstation |
| Employee-VM02 | Windows 11 Enterprise | West US 2 | Employee workstation |
| Management-VM01 | Windows 11 Enterprise | West US 2 | Management workstation |
| Wazuh-Linux-VM01 | Ubuntu 24.04 LTS | West US 3 | Security monitoring server |

## Resource Management

The Azure resources are organized under the CapStone resource group. Automatic shutdown was configured for the virtual machines at 10:00 PM Pacific Time to help manage operating costs.

## Azure Networking Resources

The following Azure resources were configured to support network connectivity and security.

| Resource | Purpose |
|---|---|
| CascadeCycling VNet | Main network for employee and management virtual machines |
| Wazuh VNet | Separate network for the Wazuh monitoring server |
| Azure Firewall | Controls traffic between the employee network and Wazuh |
| Network Security Groups (NSGs) | Manage inbound and outbound traffic for virtual machines |
| Route Table | Directs employee traffic to Wazuh through Azure Firewall |
| VNet Peering | Connects the Azure networks across the two regions |
| Log Analytics Workspace | Collects Azure Firewall logs for monitoring and testing |

The Azure Firewall was deployed in the main Cascade Cycling VNet. A route table was configured to direct traffic from the employee subnet to the Wazuh server through the firewall.
