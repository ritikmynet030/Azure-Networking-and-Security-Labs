

---

## 🔹 Step 1: Create Resource Group

- **Name:** `rg-service-endpoint1`
- **Region:** Central India

---

## 🔹 Step 2: Create Virtual Network & Subnet

### Virtual Network
- **Name:** `vnet-privateendpoint`
- **Address Space:** `10.0.0.0/16`

### Subnet
- **Name:** `AppSubnet`
- **Address Range:** `10.0.2.0/24`

⚠️ **Do NOT enable Service Endpoints**

---

## 🔹 Step 3: Create Azure Storage Account

**Storage Accounts → Create**

### Basics
- **Name:** `stprivatendpoints`
- **Region:** Same as VNet
- **Performance:** Standard
- **Redundancy:** LRS

### Networking
- **Network access:** Public endpoint  
- **Access:** All networks *(temporary)*

✅ Create the storage account

---

## 🔹 Step 4: Create Private Endpoint (MOST IMPORTANT)

### Open Storage Account  
**Networking → Private endpoint connections → + Private endpoint**

### Basics
- **Name:** `pe-storage`
- **Region:** Same as VNet

### Resource
- **Resource type:** `Microsoft.Storage/storageAccounts`
- **Resource:** `stprivatendpoints`
- **Target sub-resource:** ✅ `blob`

### Networking
- **Virtual network:** `vnet-privateendpoint`
- **Subnet:** `AppSubnet`

📌 Azure automatically assigns a **private IP**

### DNS (VERY IMPORTANT)
- **Integrate with private DNS zone:** ✅ Yes  
- **Private DNS zone created:**
