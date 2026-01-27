# Azure Firewall with User Defined Route (UDR)

## 📌 Project Overview
This project demonstrates how to secure outbound and inbound traffic for Azure Virtual Machines using Azure Firewall combined with User Defined Routes (UDR). The lab enforces all traffic from an application subnet to flow through Azure Firewall, following enterprise-grade network security best practices aligned with the AZ-104 (Microsoft Azure Administrator) exam objectives.

The implementation includes:
- Azure Firewall deployment
- Forced tunneling using UDR
- NAT, Application, and Network firewall rules
- Secure RDP access via Firewall Public IP
- Controlled outbound internet access

---

## 🎯 Objectives
- Deploy Azure Firewall with required subnets
- Route all outbound traffic from AppSubnet through Azure Firewall
- Enable secure RDP access using Firewall DNAT rules
- Allow controlled outbound web access (HTTP/HTTPS)
- Implement DNS, NTP, SSH, and RDP network rules
- Validate firewall behavior using real VM testing

## 🏗️ Architecture Summary
- **Resource Group:** rg-azure-afw
- **Region:** Central India
- **VNet:** afw-vnet (10.0.0.0/16)
- **Subnets:**
  - AzureFirewallSubnet (10.0.0.0/24)
  - AzureFirewallManagementSubnet (10.0.1.0/24)
  - AppSubnet (10.0.2.0/24)
- **Azure Firewall:** Standard SKU
- **UDR:** Forces 0.0.0.0/0 traffic via Firewall
- **VM:** Windows VM in AppSubnet

---

## 🏗️ Architecture Diagram (Logical)


---

## ⭐ Key Features Implemented
- ✅ Azure Firewall (Standard SKU)
- ✅ Mandatory Firewall Subnets configured correctly
- ✅ User Defined Route (0.0.0.0/0) to Firewall
- ✅ DNAT rule for secure RDP access
- ✅ Application rules for outbound web traffic
- ✅ Network rules for DNS, SSH, RDP, NTP
- ✅ End-to-end traffic inspection & enforcement

---

## 🧩 Azure Services Used
- Azure Virtual Network (VNet)
- Azure Firewall (Standard)
- Azure Route Table (UDR)
- Azure Public IP (Standard SKU)
- Azure Virtual Machine (Windows Server)
- Network Security Group (NSG)

---

## 🔐 Security Design
- DNAT rule for RDP via Firewall Public IP
- Application rules for HTTP/HTTPS internet access
- Network rules for DNS, NTP, SSH, RDP
- No direct internet access from VM without Firewall

---

## 🛠️ Key Skills Demonstrated
- Azure networking & subnet planning
- Enterprise firewall deployment
- Secure inbound access using DNAT
- Outbound traffic control using Application Rules
- Layer 4 vs Layer 7 traffic handling
- Route table association & forced tunneling
- Real-world troubleshooting & validation

---

## 🧪 Validation
- RDP via Firewall Public IP ✅
- Internet browsing via Firewall ✅
- ICMP blocked ❌ (expected behavior)

---

