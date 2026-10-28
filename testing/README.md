# Security Testing

## Overview

Security testing was completed to verify network access restrictions, firewall routing, and communication between the Azure virtual machines and the Wazuh monitoring server.

## Network Security Testing

Azure Network Watcher IP Flow Verify was used to test traffic between the virtual machines.

| Test | Result |
|---|---|
| Employee-VM01 to Management-VM01 (RDP) | Denied |
| Employee-VM02 to Management-VM01 (RDP) | Denied |
| Employee-VM01 to Employee-VM02 (RDP) | Denied |
| Employee-VM02 to Employee-VM01 (RDP) | Denied |
| Employee-VM01 to Wazuh (TCP 1514) | Allowed |
| Employee-VM02 to Wazuh (TCP 1514) | Allowed |

### Network Watcher Verification

Azure Network Watcher IP Flow Verify was used to confirm that RDP traffic from Employee-VM02 to Management-VM01 was denied by the Deny-Employee-to-Management NSG rule.

![Network Watcher Employee VM Denied](Network%20Watcher%20Employee%20VM%20Denied.png)

## Azure Firewall Testing

Azure Log Analytics was used to review firewall logs and verify traffic between the employee virtual machines and the Wazuh server.

The logs confirmed that both employee virtual machines were allowed to communicate with Wazuh on TCP port 1514 through Azure Firewall.

## Wazuh Monitoring

The Wazuh dashboard was used to confirm that all three Windows agents were connected and active. Security events, vulnerability findings, and configuration assessments were also reviewed through the dashboard.
