# 🔐 Azure Point-to-Site (P2S) VPN Lab 

## 🎯 Goal
Provide secure administrative access from a local machine to Azure Virtual Network resources using Point-to-Site VPN with certificate-based authentication.

This lab demonstrates how to:
- Deploy Azure VPN Gateway
- Configure P2S VPN
- Implement certificate-based authentication
- Connect from local machine
- Access private Azure VM securely

---

## 🏗 Architecture Diagram
- Local Laptop
- |
- | (P2S VPN - Certificate Authentication)
- |
- Azure VPN Gateway (vpngw-p2s)
- |
- Azure Virtual Network (10.0.0.0/16)
- |
- Private VM (No Public IP)

---

## 🛠 Technologies Used

- Azure Virtual Network
- Azure VPN Gateway (Route-Based)
- Point-to-Site VPN
- Self-Signed Certificates
- Windows VPN Client

---

## 📦 Resources Created

| Resource | Name |
|----------|------|
| Resource Group | rg-p2s-vpn |
| Virtual Network | vnet-p2s |
| VPN Gateway | vpngw-p2s |
| Test VM | vm-admin |

---

## 🔐 Security Design

- No Public IP on VM
- Encrypted VPN tunnel (IKEv2 + SSTP)
- Certificate-based authentication
- Private IP-based RDP/SSH

---

## ✅ Validation

After successful setup:

- VPN Status: Connected
- RDP to VM private IP
- Ping private IP
- No public exposure

---

## 📌 AZ-104 Concepts Covered

- VPN Gateway
- Route-Based VPN
- P2S vs S2S
- Certificate Authentication
- Secure Admin Access
- Network Isolation


