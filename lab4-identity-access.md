# Lab 4: Implement Identity and Access Management (Portal + CLI)

## Overview
Use Azure AD and RBAC to secure resources and enable managed identities.

## Architecture
![Identity Architecture](images/lab4-identity-architecture.png)

## Azure Portal Steps
1. Create Azure AD user `labuser`
2. Create group `labgroup` and add user
3. Assign Reader role to group on a resource group
4. Enable managed identity on VM
5. Grant VM access to Storage Account

## Azure CLI Steps
```bash
az ad user create --display-name "Lab User" --user-principal-name labuser@domain.onmicrosoft.com --password "YourP@ssword123"
az role assignment create --assignee labuser@domain.onmicrosoft.com --role "Reader" --scope /subscriptions/<subId>
```

## Real-World Use
- Secure access with least privilege
- Use managed identities for automation
