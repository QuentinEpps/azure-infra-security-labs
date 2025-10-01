# 🧪 Lab 3: Manage Azure Storage (Blob, File, Lifecycle)

## 📘 Objectives
- Create Storage Account
- Configure Blob and File storage
- Set access levels and lifecycle rules

## ✅ Prerequisites
- Azure subscription
- Azure CLI installed

## 🖥️ Azure Portal Steps
1. Create Storage Account `storagelab`
2. Create Blob container and upload files
3. Create File share and test access
4. Configure lifecycle rules
5. Generate SAS token

## 💻 Azure CLI Steps
```bash
az group create --name rg-storage-lab --location eastus
az storage account create --name storagelab$RANDOM --resource-group rg-storage-lab --location eastus --sku Standard_LRS
az storage container create --name labcontainer --account-name <yourStorageAccountName> --auth-mode login
az storage blob upload --account-name <yourStorageAccountName> --container-name labcontainer --name sample.txt --file ./sample.txt --auth-mode login
```

## 📝 Notes
- Document access levels and lifecycle rules
