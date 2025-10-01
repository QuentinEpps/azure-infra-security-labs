# 🧪 Lab 4: Implement Identity and Access Management

## 📘 Objectives
- Create Azure AD users and groups
- Assign RBAC roles
- Use managed identities

## ✅ Prerequisites
- Azure subscription
- Azure AD access

## 🖥️ Azure Portal Steps
1. Create users and groups in Azure AD
2. Assign roles to users/groups
3. Enable managed identity on VM
4. Grant access to Storage Account

## 💻 Azure CLI Steps
```bash
az ad user create --display-name "Lab User" --user-principal-name labuser@yourdomain.onmicrosoft.com --password "YourP@ssword123"
az role assignment create --assignee labuser@yourdomain.onmicrosoft.com --role "Reader" --scope /subscriptions/<subscriptionId>
```

## 📝 Notes
- Document role assignments and identity usage
