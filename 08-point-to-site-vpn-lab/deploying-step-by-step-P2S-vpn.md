# 🚀 Deployment Guide – Azure Point-to-Site (P2S) VPN

---

# STEP 1: Create Resource Group

- Name: `rg-p2s-vpn`
- Region: `Central India`

Purpose: Logical container for all VPN resources.

---

# STEP 2: Create Virtual Network

## Virtual Network

- Name: `vnet-p2s`
- Address Space: `10.0.0.0/16`

## Subnets

| Name | Address |
|------|----------|
| AppSubnet | 10.0.1.0/24 |
| GatewaySubnet | 10.0.255.0/27 |

⚠ GatewaySubnet name must be exactly **GatewaySubnet**

Purpose: Required for VPN Gateway deployment.

---

# STEP 3: Create VPN Gateway

Fill the following details:

- Name: `vpngw-p2s`
- Gateway Type: VPN
- VPN Type: Route-Based
- SKU: VpnGw1
- Generation: Generation1
- Virtual Network: vnet-p2s
- Public IP: Create New

⏳ Deployment time: 30–45 minutes

Purpose: Enables encrypted VPN connectivity.

---

# STEP 4: Create Certificates (Local Machine Only)

⚠ Do NOT use Azure Cloud Shell

## Create Root Certificate

Run PowerShell as Administrator:

``powershell

screenshot

## Export Root Certificate (Public Key Only)
- Open certmgr.msc
- Personal → Certificates
- Right-click P2SRootCert
- Export → No private key
- Select Base-64 encoded (.cer)
- Save as P2SRootCert.cer

