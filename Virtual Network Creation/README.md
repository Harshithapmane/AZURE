# Azure Virtual Network Creation (GUI)

## 📌 Task Overview
This lab demonstrates how to create an Azure Virtual Network (VNet) using the Azure Portal (GUI).

---

## 🔹 Requirements
- **VNet Name:** devops-vnet
- **Region:** East US
- **Address Space:** Any IPv4 CIDR block

---

## 🔹 Steps to Create VNet via Azure Portal

### Step 1: Login
- Open https://portal.azure.com
- Login using provided Azure lab credentials

---

### Step 2: Open Virtual Networks
- Search for **Virtual Networks**
- Click **+ Create**

---

### Step 3: Basics Tab
| Setting | Value |
|------|------|
| Resource Group | Existing RG |
| Name | devops-vnet |
| Region | East US |

Click **Next : IP Addresses**

---

### Step 4: IP Addresses
- IPv4 Address Space:
- Keep default subnet or proceed without changes

Click **Review + Create**

---

### Step 5: Create
- Review the configuration
- Click **Create**

---

## ✅ Verification
- Navigate to **Virtual Networks**
- Open **devops-vnet**
- Confirm:
- Region: East US
- Address Space: 10.0.0.0/16

---

## 🏁 Result
Azure Virtual Network **devops-vnet** successfully created using the Azure Portal.

---

## 📚 Learning Outcome
- Hands-on experience with Azure Portal
- Understanding VNet basics and IP addressing

---
