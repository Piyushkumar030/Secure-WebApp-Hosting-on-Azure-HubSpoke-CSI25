# 🔐 Secure Hosting of Web App via Azure Application Gateway  
## 🌐 Hub-and-Spoke Topology | Microsoft Azure | Internship Project

![Azure](https://img.shields.io/badge/Azure-Sandbox-blue?style=flat&logo=microsoft-azure)
![Project](https://img.shields.io/badge/Secure%20Cloud%20Hosting-Deployed-brightgreen)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 📁 About the Project

This project demonstrates how to **securely host a web application on Azure** using a **Hub-and-Spoke network topology**. It uses **Network Security Groups (NSGs)**, **Route Tables**, **VMs**, and **custom routing** to simulate traffic filtering via a firewall — all deployed in the **Microsoft Learn Sandbox** under limited permissions.

> 💡 Note: The real Azure Firewall service was replaced with a **SimulatedFirewallVM** due to Sandbox limitations.

---

## 🎯 Objectives

- Design a secure Azure network using hub-and-spoke topology.  
- Deploy and configure VNets, subnets, peering, and NSGs.  
- Route traffic through a simulated firewall (via custom UDR).  
- Host a sample Web VM with NSG filtering and RDP (test setup).  
- Document limitations and provide complete architecture walkthrough.

---

## ⚙️ Services & Tools Used

- **Azure Virtual Network (VNet)**
- **Subnets** with segmentation
- **Network Security Groups (NSGs)**  
- **Route Table** with custom routes  
- **Virtual Machines (Windows Server 2019)**  
- **Microsoft Learn Sandbox** (free environment)

---

## 🧱 Architecture Overview

- **Hub-VNet**: Contains `SimulatedFirewallVM`
- **Spoke-Web-VNet**: Hosts `WebVM` (application server)
- **Spoke-Storage-VNet**: Storage placeholder (no public access)
- **Peering**: Connects Spokes to Hub for centralized routing
- **Routing**: All 0.0.0.0/0 traffic forwarded to firewall VM

> 🔒 Access is restricted using NSGs + route enforcement.

---

## 🖼️ Screenshots Included

- ✅ VNets and Subnets Created  
- ✅ NSG Rules (3389 / 8080) Configured  
- ✅ Route Table + Association  
- ✅ Peering Setup  
- ✅ VM Overview Pages  
- ⚠️ RDP Timeout Screenshot (sandbox limitation shown)

---

## 📄 Project Report

The full PDF report is available in the repo:  
📎 `Secure Hosting of Web App on Azure-CSI25.pdf`

Includes:
- Step-by-step implementation  
- Screenshots for each phase  
- Description of sandbox constraints  
- Conclusion and references

---

## 🧠 Learning Outcome

This project helped build real knowledge of:

- Azure network security  
- Firewall simulation with NSG + routing  
- Practical VM setup  
- Limitations of sandboxed cloud environments

---

## 📚 References

1. [Hub-and-Spoke Network Topology – Microsoft Learn](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/hybrid-networking/hub-spoke)  
2. [Secure Azure VNets with NSG & Route Tables – Microsoft Docs](https://learn.microsoft.com/en-us/azure/virtual-network/tutorial-filter-network-traffic)

---

## 🙋 Author

**👨‍💻 Piyush Kumar Dey**  
B.Tech | Computer Science | Celebal Technology Internship  


---

> 📌 *Feel free to fork this repo, give feedback, or connect on LinkedIn!*

