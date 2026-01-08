# Azure Virtual Machine Creation Using Azure CLI

This repository demonstrates how to create an Azure Virtual Machine using the Azure CLI from the `azure-client` host without accessing the Azure portal.

---

## 📌 Task Overview

The objective is to create an Azure Virtual Machine with the following configuration:

- **VM Name:** devops-vm
- **Operating System:** Ubuntu 22.04 LTS
- **VM Size:** Standard_B2s
- **Admin Username:** azureuser
- **Authentication Method:** SSH key-based authentication
- **OS Disk Size:** 30 GB
- **Storage Type:** Standard_LRS
- **VM State:** Running after creation

---

## 🧰 Prerequisites

- Azure CLI installed
- Access to an Azure subscription
- Permission to create resources in an existing resource group
- Access to the `azure-client` (landing host)

---

## 🔍 Step 1 — Identify Existing Resource Group

Before creating the VM, list the existing resource groups and select one:

```bash
az group list -o table
