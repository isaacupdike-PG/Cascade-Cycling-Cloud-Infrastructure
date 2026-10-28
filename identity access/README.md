# Identity and Access Management

## Overview

Microsoft Entra ID and Azure Role-Based Access Control (RBAC) were used to manage user access to the Cascade Cycling virtual machines. Users were organized into groups based on their responsibilities within the company.

## User Groups

Seven user accounts were created and organized into three groups.

| Group | Users | Purpose |
|---|---|---|
| Cascade Cycling Employees | 4 | Employee workstation access |
| Cascade Cycling Management | 2 | Employee and management workstation access |
| Cascade Cycling IT admins | 1 | Administrative access to virtual machines |

## Role Assignments

Azure RBAC roles were assigned to the groups to control access to the virtual machines.

| Virtual Machine | Group | Assigned Role |
|---|---|---|
| Employee-VM01 and Employee-VM02 | Employees | Virtual Machine User Login |
| Employee-VM01 and Employee-VM02 | Management | Virtual Machine User Login |
| Employee-VM01 and Employee-VM02 | IT admins | Virtual Machine Administrator Login |
| Management-VM01 | Management | Virtual Machine User Login |
| Management-VM01 | IT admins | Virtual Machine Administrator Login |

## Authentication

Microsoft Entra ID authentication was enabled on the employee virtual machines. Administrative access was tested using Remote Desktop Protocol (RDP).
