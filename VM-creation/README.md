# Azure Virtual Machine Creation – Ubuntu 22.04

## 📌 Overview
This project demonstrates the creation of an **Azure Virtual Machine** using the **Azure Portal**, following specific infrastructure requirements.  
The goal is to provision a Linux VM with secure SSH access while keeping most configurations at their default values.

---

## 🛠️ Task Requirements

- Use an **existing Resource Group**
- VM Name: **devops-vm**
- Region: **West US**
- Operating System: **Ubuntu Server 22.04 LTS**
- VM Size: **Standard_B1s**
- Network Security Group:
  - Allow **SSH (Port 22)** inbound
- OS Disk:
  - Size: **30 GB**
  - Type: **Standard HDD**
- All other configurations kept as **default**
- Verify successful **SSH access** to the VM

---

## 🚀 Implementation Steps

### 1. Azure Portal Login
- Logged into the Azure Portal using provided lab credentials
- Verified correct subscription and existing resource group

---

### 2. Virtual Machine Creation
- Navigated to **Virtual Machines → Create → Azure Virtual Machine**
- Selected the existing resource group
- Entered VM name as `devops-vm`
- Selected **West US** as the region
- Chose **Ubuntu Server 22.04 LTS** image
- Selected VM size **Standard_B1s**

---

### 3. Disk Configuration
- Configured OS disk size to **30 GB**
- Selected **Standard HDD** as the disk type
- Left remaining disk options as default

---

### 4. Networking Configuration
- Used default Virtual Network and Subnet
- Created a Public IP address
- Attached a **default Network Security Group**
- Allowed inbound **SSH (Port 22)** access

---

### 5. Review and Create
- Reviewed all configurations
- Successfully deployed the virtual machine

---

## 🔐 SSH Verification

After deployment, SSH access was tested successfully using the VM’s public IP:

```bash
ssh azureuser@<public-ip-address>
