# 🧪 Lab 5: Monitor and Secure Resources with Defender for Cloud

## 📘 Objectives
- Enable Defender for Cloud
- Review Secure Score
- Simulate alerts and enable JIT access

## ✅ Prerequisites
- Azure subscription
- Defender for Cloud enabled

## 🖥️ Azure Portal Steps
1. Enable Defender for Cloud
2. Review Secure Score and recommendations
3. Simulate threat and review alerts
4. Enable Just-in-Time VM access

## 💻 Azure CLI Steps
```bash
az security pricing create --name VirtualMachines --tier Standard
az security task list --resource-group <yourResourceGroup>
```

## 📝 Notes
- Document Secure Score and remediation actions
