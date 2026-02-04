# Azure Site-to-Site VPN – Hybrid Connectivity Lab 

## 📌 Overview
This project demonstrates how to configure an **Azure Site-to-Site (S2S) VPN** to establish **hybrid connectivity** between an Azure Virtual Network and an on-premises network (simulated).

---

## 🎯 Objectives
- Create Azure networking components for hybrid connectivity
- Deploy and configure a **Route-Based VPN Gateway**
- Simulate an on-premises network using Azure
- Establish secure **IPsec/IKE-encrypted communication**
- Validate connectivity

---

## 🏗️ Architecture

Azure VNet (10.0.0.0/16)
- AppSubnet: 10.0.1.0/24
- GatewaySubnet: 10.0.255.0/27

On-Prem (Simulated)
- Address space: 10.1.0.0/16
- Public IP: Simulated firewall IP

Secure Tunnel
- Site-to-Site VPN
- IPsec / IKEv2

---

## 🔐 Security
- Encrypted IPsec tunnel
- Shared Key authentication
- Enterprise IKE/IPsec policies

---

## 🧪 Validation
- VPN status shows **Connected**
- VM communication across networks
- Successful ping / RDP / SSH
