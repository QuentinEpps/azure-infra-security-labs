# Lab 3: Manage Azure Storage (Portal + CLI)

## Overview
Create and manage storage accounts, blob containers, and file shares.

## Architecture
![Storage Architecture](images/lab3-storage-architecture.png)

## Azure Portal Steps
1. Create Storage Account `storagelab`
2. Create Blob container `labcontainer` and upload file
3. Create File share `labshare` and upload file
4. Configure lifecycle rules
5. Generate SAS token

## Azure CLI Steps
```bash
az group create --name rg-storage-lab --location eastus
az storage account create --name storagelab$RANDOM --resource-group rg-storage-lab --location eastus --sku Standard_LRS
az storage container create --name labcontainer --account-name <name> --auth-mode login
az storage blob upload --account-name <name> --container-name labcontainer --name sample.txt --file ./sample.txt --auth-mode login
```

## Real-World Use
- Store logs, backups, and static content
- Use lifecycle rules to reduce costs
