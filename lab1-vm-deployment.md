# 🧪 Lab 1: Deploy Windows and Linux VMs (Portal + CLI)

## 📘 Objectives
- Deploy Windows Server and Ubuntu Linux VMs
- Configure NSGs and public IPs
- Connect via RDP and SSH
- Compare Portal vs CLI deployment

## ✅ Prerequisites
- Azure subscription
- Azure CLI installed
- Remote Desktop and SSH clients

## 🖥️ Azure Portal Steps
1. Create Resource Group `rg-lab-vms`
2. Deploy Windows Server 2022 VM
3. Deploy Ubuntu Linux VM
4. Configure NSGs for RDP (3389) and SSH (22)
5. Connect and install IIS/NGINX

## 💻 Azure CLI Steps
```bash
az group create --name rg-lab-vms --location eastus
az vm create --resource-group rg-lab-vms --name win-vm01 --image Win2022Datacenter --admin-username azureuser --admin-password YourP@ssword123 --size Standard_B2s
az vm open-port --port 3389 --resource-group rg-lab-vms --name win-vm01
az vm create --resource-group rg-lab-vms --name linux-vm01 --image UbuntuLTS --admin-username azureuser --generate-ssh-keys --size Standard_B2s
az vm open-port --port 22 --resource-group rg-lab-vms --name linux-vm01
```

## 📝 Notes
- Document IPs, credentials, and installation steps
