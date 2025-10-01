# 🧪 Lab 5: Monitor and Secure Resources with Defender for Cloud

## 🎯 Objectives
Enable Defender for Cloud, review Secure Score, and simulate alerts.

## 🧱 Architecture Overview
![Defender Architecture](images/lab5-defender-architecture.png)

## ✅ Prerequisites
- Azure subscription
- Defender for Cloud enabled

## 🖥️ Step-by-Step Instructions

### 1. Enable Defender for Cloud
```bash
az security pricing create --name VirtualMachines --tier Standard
```

### 2. Review Secure Score
```bash
az security secure-score list
```
**Why:** Secure Score helps identify security gaps.

## 🧠 Real-World Application
- Monitor compliance and threats
- Enable JIT access to reduce attack surface

## 📝 Notes
- Document alerts and remediation actions
