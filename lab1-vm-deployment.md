# 🧪 Lab 1: Deploy Windows and Linux VMs (Portal + CLI)

## 🎯 Objectives
Learn to deploy Windows and Linux virtual machines using both the Azure Portal and CLI. Understand VM sizing, networking, and access methods. Apply this to real-world scenarios like hosting applications or jumpboxes.

## 🧱 Architecture Overview
![VM Deployment Architecture](images/lab1-vm-architecture.png)

## ✅ Prerequisites
- Azure subscription
- Azure CLI installed
- Remote Desktop and SSH clients

## 🖥️ Step-by-Step Instructions

### 1. Create a Resource Group
**Why:** Logical container for related resources.
```bash
az group create --name rg-lab-vms --location eastus
```
This command creates a resource group named `rg-lab-vms` in the East US region.

### 2. Deploy Windows VM
**Why:** Windows VMs are commonly used for legacy apps, domain controllers, or jumpboxes.
```bash
az vm create   --resource-group rg-lab-vms   --name win-vm01   --image Win2022Datacenter   --admin-username azureuser   --admin-password YourP@ssword123   --size Standard_B2s
```
This command provisions a Windows Server 2022 VM with basic specs.

### 3. Open RDP Port
**Why:** Allow remote desktop access.
```bash
az vm open-port --port 3389 --resource-group rg-lab-vms --name win-vm01
```

### 4. Deploy Linux VM
**Why:** Linux VMs are used for web servers, containers, and automation.
```bash
az vm create   --resource-group rg-lab-vms   --name linux-vm01   --image UbuntuLTS   --admin-username azureuser   --generate-ssh-keys   --size Standard_B2s
```

### 5. Open SSH Port
```bash
az vm open-port --port 22 --resource-group rg-lab-vms --name linux-vm01
```

## 🧠 Real-World Application
- Use Windows VM as a jumpbox to access private resources
- Host web apps on Linux VM with NGINX or Apache

## 📝 Notes
- Record public IPs and credentials securely
- Test connectivity and install basic tools
