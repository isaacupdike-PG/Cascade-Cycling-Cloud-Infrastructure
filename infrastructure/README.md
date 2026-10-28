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
