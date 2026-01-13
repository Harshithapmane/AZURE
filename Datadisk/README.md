# 🚀 Attach Existing Data Disk to Azure Virtual Machine

---

## 📌 Task Overview

Attach an existing **managed data disk** to an existing **Azure Virtual Machine** and verify it inside the **Linux (Ubuntu 22.04)** operating system.

---

## 🎯 Objective

- Attach the existing managed disk **datacenter-disk** to **datacenter-vm**
- Ensure the disk is successfully attached
- Verify disk visibility inside the VM
- Confirm virtual machine initialization is complete

---

## 🖥️ Method 1: Azure Portal (GUI)

### Step 1: Login to Azure Portal

- Go to: https://portal.azure.com  
- Sign in using the provided Azure credentials

---

### Step 2: Open the Virtual Machine

- Search for **Virtual Machines**
- Select **datacenter-vm**
- Ensure the VM status is **Running**

---

### Step 3: Attach Existing Data Disk

- In the VM menu, click **Disks**
- Under **Data disks**, click **+ Add data disk**
- Select the existing disk: **datacenter-disk**
- Click **Save**
- Wait for **Update succeeded** notification

✅ **Disk is now attached at the Azure level**

---

## 🔍 Verification in Azure Portal

- Navigate to **Virtual Machine → Disks**
- Confirm **datacenter-disk** appears under **Data disks**
- Disk status should be **Attached**

---

## 🐧 Method 2: Verify Inside Linux VM (Ubuntu 22.04)

### Step 4: Connect to the VM

```bash
ssh <username>@<public-ip>
Step 5: List Attached Disks
lsblk


Example output:

sda    30G  disk
└─sda1 30G  part /
sdc    32G  disk


👉 sdc indicates the newly attached data disk

💾 (Optional) Initialize & Mount Disk
Create Partition
sudo fdisk /dev/sdc


n → new partition

p → primary

Press Enter for default values

w → write changes

Create Filesystem
sudo mkfs.ext4 /dev/sdc1

Mount Disk
sudo mkdir /datadisk
sudo mount /dev/sdc1 /datadisk


Verify mount:

df -h

⚡ Method 3: Azure CLI (Optional)
Attach Disk Using CLI
az vm disk attach \
  --resource-group <RESOURCE_GROUP_NAME> \
  --vm-name datacenter-vm \
  --name datacenter-disk

Verify Disk Attachment
az vm show \
  --resource-group <RESOURCE_GROUP_NAME> \
  --name datacenter-vm \
  --query "storageProfile.dataDisks[].name" \
  -o table

✅ Final Validation Checklist

 VM datacenter-vm is running

 Disk datacenter-disk attached as Data Disk

 Disk visible in Azure Portal

 Disk visible using lsblk

 VM initialization completed

🏁 Result

Successfully attached an existing managed data disk to an Azure Virtual Machine and verified it inside a Linux (Ubuntu 22.04) operating system.
