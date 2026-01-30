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
- │
- │ Service Endpoint (Microsoft.Storage)
- ▼
- Azure Storage Account
(Selected Networks Only)

---

### 🔧 Implementation Steps

1. Create Resource Group  
2. Create VNet and AppSubnet  
3. Enable **Microsoft.Storage** Service Endpoint on subnet  
4. Create Storage Account  
5. Restrict storage access to **Selected Networks**  
6. Allow access only from AppSubnet  

---

### 🧪 Validation & Testing

#### ❌ From Local PC
- Access Storage via Portal / Storage Explorer
- **Result:** `403 Forbidden`

#### ✅ From VM in AppSubnet
- Create container / upload blob
- **Result:** Access allowed

---

### 📌 Key Takeaways

- Uses public endpoint
- No DNS changes required
- Free of cost
- Common in mid-level enterprise environments

---
---

## 🧪 Lab 7: Private Endpoint (Zero Public Exposure)

### 🎯 Objective
Provide **private IP-based access** to Azure Storage with **public access completely disabled**.

---

### 🧠 Key Concept
Private Endpoints assign a **private IP from the VNet** to a PaaS service and require **Private DNS integration**.

---

### 🏗 Architecture

VNet (10.0.0.0/16)
└── AppSubnet (10.0.2.0/24)
- │
- │ Private IP (10.0.2.x)
- ▼
- Azure Storage Account
(Public Access Disabled)
