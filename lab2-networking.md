# Lab 2: Configure Azure Networking for VMs (Portal + CLI)

## Overview
Create VNets, subnets, and NSGs to isolate and secure VM traffic.

## Architecture
![Networking Architecture](images/lab2-networking-architecture.png)

## Azure Portal Steps
1. Create VNet `vnet-lab` with address space `10.0.0.0/16`
2. Add subnets:
   - `subnet-windows`: `10.0.1.0/24`
   - `subnet-linux`: `10.0.2.0/24`
3. Create NSGs and add inbound rules for RDP and SSH
4. Associate NSGs with subnets or NICs
5. Deploy VMs into subnets
6. Test connectivity between VMs

## Azure CLI Steps
```bash
az group create --name rg-network-lab --location eastus
az network vnet create --resource-group rg-network-lab --name vnet-lab --address-prefix 10.0.0.0/16 --subnet-name subnet-windows --subnet-prefix 10.0.1.0/24
az network vnet subnet create --resource-group rg-network-lab --vnet-name vnet-lab --name subnet-linux --address-prefix 10.0.2.0/24
az network nsg create --resource-group rg-network-lab --name nsg-windows
az network nsg rule create --resource-group rg-network-lab --nsg-name nsg-windows --name allow-rdp --protocol Tcp --direction Inbound --priority 1000 --source-address-prefix '*' --source-port-range '*' --destination-address-prefix '*' --destination-port-range 3389 --access Allow
```

## Real-World Use
- Isolate workloads by subnet
- Secure VMs with NSGs
