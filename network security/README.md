# Network Security

## Overview

Network security for Cascade Cycling was configured using Azure Firewall, Network Security Groups (NSGs), and custom routing. These controls were used to restrict access between virtual machines and manage communication with the Wazuh monitoring server.

## Network Security Groups

NSGs were configured on the virtual machine network interfaces to control inbound and outbound traffic.

The following restrictions were implemented on the employee virtual machines:

| Rule | Purpose |
|---|---|
| Deny-Employee-to-Management | Blocks employee subnet traffic to the management subnet |
| Deny-Employee-to-Employee-RDP | Blocks RDP connections between employee virtual machines |
| Allow-RDP-Temp | Allows temporary administrative RDP access from a restricted source IP |

The employee-to-management restriction was configured for all protocols, while the employee-to-employee restriction specifically targeted RDP traffic on TCP port 3389.

## Azure Firewall

Azure Firewall was deployed in the main Cascade Cycling virtual network to manage traffic between the employee subnet and the Wazuh monitoring server.

Firewall rules were configured to allow communication with Wazuh using TCP ports 1514 and 1515.

## Routing

## Routing

A custom route table was configured on the employee subnet to direct traffic destined for the Wazuh monitoring server through Azure Firewall.

The route, named `Route-to-Wazuh`, directs traffic for the Wazuh server (`172.16.0.4/32`) to Azure Firewall (`10.10.4.4`) before it reaches the monitoring network.
