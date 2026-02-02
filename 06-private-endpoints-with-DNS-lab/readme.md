# 🚀 Azure Private DNS with Private Endpoint (Enterprise Lab – AZ-104)

This project demonstrates **enterprise-grade Azure Private DNS implementation** integrated with **Azure Private Endpoints** to enable **secure, private name resolution for Azure PaaS services** without public internet exposure.

---

## 🎯 Objectives

- Create and configure **Azure Private DNS Zone**
- Link Private DNS Zone to a **Virtual Network**
- Integrate **Private Endpoint** with Private DNS
- Validate **private name resolution**
- Ensure traffic remains **inside Azure network**

---

## 🧠 What is Azure Private DNS?

Azure Private DNS provides **private DNS name resolution within a Virtual Network** without relying on public DNS servers.

It is primarily used with:
- Azure Private Endpoints
- Azure PaaS services (Storage, SQL, Key Vault, Web Apps)
- Zero Trust and private-only architectures

---

## ❓ Why Private DNS is Critical (Enterprise Perspective)

Without Private DNS:
- PaaS services resolve to **public IPs**
- Traffic may leave Azure network
- Security and compliance risks increase

With Private DNS:
- Services resolve to **private IPs**
- No public exposure
- Automatic DNS record management
- Fully compliant with enterprise security standards

---

## 🏗️ Architecture Overview

> Azure VM resolves Azure PaaS service FQDN using Private DNS, which maps to a Private Endpoint inside the VNet.

- VM (VNet)
- |
- | DNS Query
- v
- Private DNS Zone
- |
- v
- Private Endpoint → Azure PaaS Service
