# 🧪 Lab 2: Configure Azure Networking for VMs

## 📘 Objectives
- Create VNet and subnets
- Assign NSGs
- Deploy VMs into subnets
- Test connectivity

## ✅ Prerequisites
- Azure subscription
- Existing VMs or new deployments

## 🖥️ Azure Portal Steps
1. Create VNet `vnet-lab` with address space `10.0.0.0/16`
2. Create subnets `subnet-windows` and `subnet-linux`
3. Create NSGs and allow RDP/SSH
4. Associate NSGs with subnets
5. Deploy VMs into subnets
6. Test ping and access

## 💻 Azure CLI Steps
```bash
az group create --name rg-network-lab --location eastus
az network vnet create --resource-group rg-network-lab --name vnet-lab --address-prefix 10.0.0.0/16 --subnet-name subnet-windows --subnet-prefix 10.0.1.0/24
az network vnet subnet create --resource-group rg-network-lab --vnet-name vnet-lab --name subnet-linux --address-prefix 10.0.2.0/24
az network nsg create --resource-group rg-network-lab --name nsg-windows
az network nsg create --resource-group rg-network-lab --name nsg-linux
az network nsg rule create --resource-group rg-network-lab --nsg-name nsg-windows --name allow-rdp --protocol Tcp --direction Inbound --priority 1000 --source-address-prefix '*' --source-port-range '*' --destination-address-prefix '*' --destination-port-range 3389 --access Allow
az network nsg rule create --resource-group rg-network-lab --nsg-name nsg-linux --name allow-ssh --protocol Tcp --direction Inbound --priority 1000 --source-address-prefix '*' --source-port-range '*' --destination-address-prefix '*' --destination-port-range 22 --access Allow
```

## 📝 Notes
- Document subnet setup and NSG rules
