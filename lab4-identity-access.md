# 🧪 Lab 4: Implement Identity and Access Management

## 🎯 Objectives
Use Azure AD and RBAC to secure resources. Enable managed identities.

## 🧱 Architecture Overview
![Identity Architecture](images/lab4-identity-architecture.png)

## ✅ Prerequisites
- Azure subscription
- Azure AD access

## 🖥️ Step-by-Step Instructions

### 1. Create Azure AD User
```bash
az ad user create --display-name "Lab User" --user-principal-name labuser@domain.onmicrosoft.com --password "YourP@ssword123"
```

### 2. Assign Role
```bash
az role assignment create --assignee labuser@domain.onmicrosoft.com --role "Reader" --scope /subscriptions/<subId>
```
**Why:** RBAC controls access to resources.

## 🧠 Real-World Application
- Grant least privilege access to teams
- Use managed identities for secure automation

## 📝 Notes
- Document role assignments and test access
