# Security Monitoring

## Overview

Wazuh was deployed to provide centralized security monitoring for the Cascade Cycling Azure environment. The Wazuh server runs on an Ubuntu virtual machine and collects security information from the Windows virtual machines.

## Wazuh Deployment

The Wazuh platform was installed on `Wazuh-Linux-VM01` using the single-node installation method. This setup includes the Wazuh manager, indexer, and dashboard.

Wazuh agents were installed on the three Windows virtual machines:

- Employee-VM01
- Employee-VM02
- Management-VM01

All three agents were connected to the Wazuh server and confirmed active.

![Wazuh Agent Overview](Wazuh%20Agent%20Overview.png)

## Security Monitoring

Wazuh was used to collect and review security information from the connected virtual machines. The monitoring features included:

- Security event collection and analysis
- Authentication activity monitoring
- Vulnerability detection
- Security configuration assessments

The Wazuh dashboard was used to review detected events, vulnerabilities, and system configuration findings.

![Wazuh Vulnerability Detection](Wazuh%20Vulnerability%20Detection.png)

## Azure Firewall Logging

Azure Firewall diagnostic logs were collected through Azure Log Analytics.

Log queries were used to verify that traffic from both employee virtual machines was allowed through Azure Firewall to the Wazuh server on TCP port 1514.
