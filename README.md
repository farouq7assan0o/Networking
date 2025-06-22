# Networking and Infrastructure Design Project

## Overview

This project documents the design and implementation of a secure and scalable network infrastructure for an enterprise environment. The project includes LAN and WAN configuration, server deployment, IP addressing and subnetting, router setup using OSPF, and validation through detailed testing procedures. The network is built to support growth and high availability through redundancy and robust design.

## Project Structure

### Locations

- Amman Site: Includes two LAN networks
- WAN: Full-mesh topology with five interconnected routers

## Infrastructure Components

### Devices and Servers

- Servers (with static IPs):
  - FTP Server
  - Email Server
  - HTTP Server (HTTPS only)
  - DNS Server
  - DHCP Server
- Network devices:
  - Switches
  - Routers
  - Printers (wired and wireless)
  - Wi-Fi Access Points
- Clients: DHCP-configured desktops and laptops

### Subnetting and IP Allocation

- Base Network: 172.16.16.0/24
- Subnet Mask: /27 (255.255.255.224)
- Hosts per subnet: 30
- Current Networks: 
  - 172.16.16.0
  - 172.16.16.32
  - 172.16.16.64
  - 172.16.16.96
  - 172.16.16.128
- Reserved for future use:
  - 172.16.16.160
  - 172.16.16.192
  - 172.16.16.224

## Server Configuration

| Server Type | IP Address     | Configuration Summary                          |
|-------------|----------------|-----------------------------------------------|
| HTTP        | 172.16.16.6    | HTTPS only                                     |
| DNS         | 172.16.16.7    | Maps domain names to IP addresses              |
| FTP         | 172.16.16.8    | Permission levels for employees and admins     |
| Email       | 172.16.16.9    | Domain-based communication (e.g., @jgames.com) |
| DHCP        | 172.16.16.10   | Serves IPs to all LAN clients                  |

## Router Configuration

- Interfaces configured with IP address and subnet mask
- Used `ip helper-address` for DHCP forwarding
- OSPF protocol configured for routing
- Passive interfaces used for LAN security
- Redundant full-mesh topology to avoid single points of failure
- Dual-password security for routers (console and enable secret)

## Testing and Validation

| Component   | Method or Command            | Expected Outcome                               |
|------------|------------------------------|------------------------------------------------|
| Device connectivity | ping                  | Successful replies between hosts               |
| Routing tables     | show ip route          | All routes visible via OSPF                    |
| FTP server         | FTP + put/get commands | File upload/download successful                |
| Email server       | Email client config    | Emails sent and received between devices       |
| DNS server         | nslookup               | Correct resolution of domain names             |
| DHCP server        | DHCP configuration     | Successful IP assignment across LANs           |
| HTTP server        | Web browser            | Secure access to internal HTTPS site           |

## Maintenance Plan

| Frequency   | Maintenance Activities                                 |
|-------------|--------------------------------------------------------|
| Daily       | Backup status, server logs                             |
| Weekly      | Software licenses, check infected devices              |
| Monthly     | OS updates, review latency and response time           |
| Bi-Annually | Restart unused services, audit security logs           |
| Annually    | Update network diagrams, rotate service account keys   |

## Skills and Knowledge Gained

- Subnetting and IP planning
- Switch and router configuration with CLI
- DHCP, DNS, FTP, Email, and HTTP server setup
- OSPF dynamic routing and IP helper configuration
- Secure router and network design
- Full functional and performance testing
- Preventative maintenance planning
- Redundancy and high-availability setup

## Recommendations for Improvement

- Implement firewall security across external interfaces
- Use unique passwords for all employee and administrator accounts
- Upgrade data transmission speed between LANs and WANs
- Use VLANs for traffic segmentation and additional security
- Expand DHCP pools and IP subnets for future scalability

## Limitations

- Requires significant cabling and hardware for full mesh redundancy
- DHCP failure could disrupt IP assignment for many devices
- Shared passwords reduce individual account security
- Some features could benefit from enterprise firewall or IDS integration

## Author

Farouq Hassan  
Fall 2022  
HTU – Networking and Systems Design
