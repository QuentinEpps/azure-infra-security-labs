# 🧪 Lab 2: Configure Azure Networking for VMs

## 🎯 Objectives
Create and configure VNets, subnets, and NSGs. Understand network isolation and security.

## 🧱 Architecture Overview
![Networking Architecture](images/lab2-networking-architecture.png)

## ✅ Prerequisites
- Azure subscription
- Existing or new VMs

## 🖥️ Step-by-Step Instructions

### 1. Create VNet and Subnets
```bash
az network vnet create   --resource-group rg-network-lab   --name vnet-lab   --address-prefix 10.0.0.0/16   --subnet-name subnet-windows   --subnet-prefix 10.0.1.0/24

az network vnet subnet create   --resource-group rg-network-lab   --vnet-name vnet-lab   --name subnet-linux   --address-prefix 10.0.2.0/24
```
**Why:** Subnets allow segmentation of workloads.

### 2. Create NSGs and Rules
```bash
az network nsg create --resource-group rg-network-lab --name nsg-windows
az network nsg rule create --resource-group rg-network-lab --nsg-name nsg-windows --name allow-rdp --protocol Tcp --direction Inbound --priority 1000 --source-address-prefix '*' --source-port-range '*' --destination-address-prefix '*' --destination-port-range 3389 --access Allow
```
**Why:** NSGs control traffic flow and security.

## 🧠 Real-World Application
- Isolate front-end and back-end tiers
- Secure VMs with least privilege access

## 📝 Notes
- Document subnet and NSG configurations
