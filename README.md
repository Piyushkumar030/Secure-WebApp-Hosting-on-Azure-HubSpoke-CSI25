
# 🔐 Secure Azure WebApp Hosting using Hub-Spoke Architecture – CSI'25

This project demonstrates secure hosting of a web application on Microsoft Azure using a Hub-Spoke network topology. It ensures isolation, custom DNS resolution, traffic filtering, and centralized security through services like Azure Firewall, Application Gateway, and Bastion.

---

## 📌 Project Overview

| Component              | Purpose                                                      |
|------------------------|--------------------------------------------------------------|
| **Hub VNet**           | Centralized security controls (Firewall, App Gateway, DNS VM) |
| **Spoke-Web VNet**     | Hosts the Web Application (Azure App Service or VM)          |
| **Spoke-Storage VNet** | Hosts secure Storage Account (no public access)              |
| **Azure Firewall**     | Filters all traffic and logs activity centrally              |
| **Application Gateway**| Handles SSL Offloading, Custom Routing, and Public Entry     |
| **DNS Forwarder VM**   | Resolves Azure and on-prem DNS queries privately             |
| **Azure Bastion**      | Secure VM access without public IPs                          |

---

## 🎯 Objectives

1. Implement Hub-Spoke architecture with centralized security
2. Configure private DNS forwarding between VNets and on-prem
3. Route all traffic through Azure Firewall
4. Set up Application Gateway with:
   - Public & Private frontend
   - SSL Offloading
   - Custom listeners & routing
5. Host WebApp securely with no direct public exposure
6. Securely store data in private Storage Account

---

## 🛠 Technologies Used

- Microsoft Azure (Sandbox)
- Virtual Networks (VNets)
- Azure Firewall
- Azure Application Gateway
- Azure Bastion
- Network Peering
- DNS Forwarder (Windows Server 2019)
- Storage Account (Private)
- App Service or VM-based WebApp Hosting
- SSL Certificate (self-signed or managed)

---

## 🔧 Setup Summary

1. ✅ Created Hub VNet with 3 subnets:
   - AzureFirewallSubnet
   - AzureFirewallManagementSubnet
   - HubSubNet

2. ✅ Created Spoke VNets:
   - `Spoke-Web-VNet` with `WebSubnet`
   - `Spoke-Storage-VNet` with `StorageSubnet`

3. ✅ Established VNet peering between Hub ↔ Web & Hub ↔ Storage

4. ✅ Deployed:
   - DNS Forwarder VM in HubSubNet
   - Installed DNS Role
   - Added 8.8.8.8 as forwarder

5. ✅ Configured custom DNS settings in all VNets pointing to DNS VM

6. ✅ Deployed Azure Firewall + Public IP

7. ✅ Deployed Application Gateway with:
   - SSL Certificate
   - Multi-listener routing
   - Frontend IPs (Public & Private)
   - Backend pool with WebApp

8. ✅ Enabled SSL Offloading and HTTP → HTTPS redirection

---

## 🔒 Security Highlights

- No public access to Storage Account
- WebApp accessed only via App Gateway
- DNS traffic resolved securely via DNS VM
- RDP access via Bastion or whitelisted IPs
- Centralized logging & control with Azure Firewall

---

## 📸 Screenshots

> Folder: `screenshots/`

- VNet and Peering setup
- DNS Forwarder configuration
- Application Gateway routing
- WebApp output via App Gateway

---

## 📁 Folder Structure

```plaintext
secure-azure-webapp-hubspoke-csi25/
│
├── screenshots/
│   └── (project images here)
│
├── dns/
│   └── dns-config.txt
│
├── gateway/
│   └── ssl-cert-info.txt
│
├── terraform/ (optional if used)
│   └── main.tf
│
└── README.md
