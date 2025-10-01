# 🧪 Lab 3: Manage Azure Storage (Blob, File, Lifecycle)

## 🎯 Objectives
Create and manage storage accounts, blob containers, and file shares. Implement lifecycle rules.

## 🧱 Architecture Overview
![Storage Architecture](images/lab3-storage-architecture.png)

## ✅ Prerequisites
- Azure subscription
- Azure CLI installed

## 🖥️ Step-by-Step Instructions

### 1. Create Storage Account
```bash
az storage account create   --name storagelab$RANDOM   --resource-group rg-storage-lab   --location eastus   --sku Standard_LRS
```
**Why:** Centralized storage for apps, logs, backups.

### 2. Create Blob Container and Upload File
```bash
az storage container create --name labcontainer --account-name <name> --auth-mode login
az storage blob upload --account-name <name> --container-name labcontainer --name sample.txt --file ./sample.txt --auth-mode login
```

## 🧠 Real-World Application
- Store app logs, backups, and static content
- Use lifecycle rules to reduce costs

## 📝 Notes
- Test access levels and SAS tokens
