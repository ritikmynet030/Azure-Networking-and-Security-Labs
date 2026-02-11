# 🔧 Lab Setup

## Step 1: Create Resource Group

- **Name:** rg-networkwatcher-lab  
- **Region:** Central India  

---

## Step 2: Create Virtual Network

- **Name:** vnet-nw-lab  
- **Address Space:** 10.10.0.0/16  

### Subnet
- **Name:** AppSubnet  
- **Address Range:** 10.10.1.0/24  

---

## Step 3: Create Virtual Machine

- **Name:** vm-test  
- **OS:** Windows or Linux  
- **Public IP:** Enabled  
- **Subnet:** AppSubnet  

---

## Step 4: Create Network Security Group (NSG)

Attach NSG to subnet or VM NIC.

### Add Rules:
- ✅ Allow RDP (3389) or SSH (22)  
- ❌ Deny TCP 8080 (for testing IP Flow Verify)

---

# 🔎 1️⃣ IP Flow Verify

## 🎯 Purpose
Checks whether traffic is allowed or denied by NSG.

## Steps

1. Go to **Network Watcher**
2. Select Region
3. Click **IP Flow Verify**
4. Select:
   - VM: vm-test
   - Direction: Inbound
   - Protocol: TCP
   - Local Port: 8080
   - Remote IP: Your public IP
5. Click **Check**

## ✅ Expected Result

- If blocked → **Deny**
- If allowed → **Allow**
- Displays matched NSG rule

---

# 🔀 2️⃣ Next Hop

## 🎯 Purpose
Identifies where traffic is routed next.

## Steps

1. Network Watcher → **Next Hop**
2. Select:
   - Source: VM private IP
   - Destination: 8.8.8.8
3. Click **Check**

## ✅ Possible Results

- Internet  
- Virtual Appliance  
- VNet Peering  
- None  

---

# 🌐 3️⃣ Connection Troubleshoot

## 🎯 Purpose
Tests real connectivity between VM and destination.

## Steps

1. Network Watcher → **Connection troubleshoot**
2. Source: vm-test
3. Destination:
   - IP: 8.8.8.8
   - Port: 443
4. Click **Check**

## ✅ Output

- Reachable / Unreachable
- Latency
- Failure point (NSG / Route / Firewall)

---

# 📦 4️⃣ Packet Capture

## 🎯 Purpose
Captures live traffic from VM (Similar to Wireshark).

## Steps

1. Network Watcher → **Packet Capture**
2. Select VM
3. Choose Storage Account
4. Filter:
   - Protocol: TCP
   - Port: 80 or 443
5. Start Capture

### Generate Traffic Inside VM

``bash
- ping 8.8.8.8  OR
- Open: https://google.com
