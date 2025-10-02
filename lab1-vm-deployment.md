# Lab 1: Deploy Windows and Linux VMs (Portal + CLI)

## Overview
Deploy Windows and Linux virtual machines using Azure Portal and CLI.

## Architecture
![VM Deployment Architecture](images/lab1-vm-architecture.png)

## Azure Portal Steps
1. Create a Resource Group named `rg-lab-vms`
2. Create a Windows Server 2022 VM
   - Size: Standard_B2s
   - Username/password
   - Enable RDP (port 3389)
3. Create an Ubuntu Linux VM
   - Use SSH key or password
   - Enable SSH (port 22)
4. Review NSG rules and public IPs
5. Connect to VMs via RDP and SSH

## Azure CLI Steps
```bash
az group create --name rg-lab-vms --location eastus
az vm create --resource-group rg-lab-vms --name win-vm01 --image Win2022Datacenter --admin-username azureuser --admin-password YourP@ssword123 --size Standard_B2s
az vm open-port --port 3389 --resource-group rg-lab-vms --name win-vm01
az vm create --resource-group rg-lab-vms --name linux-vm01 --image UbuntuLTS --admin-username azureuser --generate-ssh-keys --size Standard_B2s
az vm open-port --port 22 --resource-group rg-lab-vms --name linux-vm01
```

## Real-World Use
- Windows VM as a jumpbox
- Linux VM for hosting web apps
