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

🖥️ Step 2 — Create the Azure Virtual Machine

Run the following Azure CLI command to create the VM:

az vm create \
  --resource-group devops-rg \
  --name devops-vm \
  --image Ubuntu2204 \
  --size Standard_B2s \
  --admin-username azureuser \
  --generate-ssh-keys \
  --storage-sku Standard_LRS \
  --os-disk-size-gb 30

🔎 What This Command Does

Uses Ubuntu 22.04 LTS

Sets VM size to Standard_B2s

Creates the admin user azureuser

Automatically generates SSH keys

Creates a 30 GB OS disk

Uses Standard_LRS storage

Automatically starts the VM after creation
