# 🔐 Azure Private Access Labs (AZ-104 | Enterprise Networking)

This repository demonstrates **secure access to Azure PaaS services** using:

- **Service Endpoints** (Subnet-level security)
- **Private Endpoints** (Zero public exposure – enterprise standard)

These labs align with **AZ-104 (Microsoft Azure Administrator)** and real-world cloud security practices.

---

## 📌 Labs Covered

| Lab | Topic | Security Level |
|----|------|---------------|
| Lab 1 | Service Endpoints | Medium |
| Lab 2 | Private Endpoints | High (Enterprise) |

---

## 🧪 Lab 1: Service Endpoint

### 🎯 Objective
Secure Azure Storage access so it is **allowed only from a specific VNet subnet** and blocked from the public internet.

---

### 🧠 Key Concept
Service Endpoints extend the **VNet identity** to Azure PaaS services while still using **public endpoints**.

---

### 🏗 Architecture

VNet (10.0.0.0/16)
└── AppSubnet (10.0.2.0/24)
│
│ Service Endpoint (Microsoft.Storage)
▼
Azure Storage Account
(Selected Networks Only)
