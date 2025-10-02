# Lab 5: Monitor and Secure Resources with Defender for Cloud (Portal + CLI)

## Overview
Enable Defender for Cloud, review Secure Score, and simulate alerts.

## Architecture
![Defender Architecture](images/lab5-defender-architecture.png)

## Azure Portal Steps
1. Enable Defender for Cloud for subscription
2. Review Secure Score and recommendations
3. Simulate threat (e.g., open port 3389)
4. Enable Just-in-Time VM access
5. Review alerts and remediation steps

## Azure CLI Steps
```bash
az security pricing create --name VirtualMachines --tier Standard
az security secure-score list
```

## Real-World Use
- Monitor compliance and threats
- Reduce attack surface with JIT access
