# **Disk Partitioning (Ubuntu – MBR & Windows – GPT)**

## **Overview**

This task demonstrates how to create and manage disk partitions using:

* **MBR (Master Boot Record)** in Ubuntu Linux

* **GPT (GUID Partition Table)** in Windows

The goal of this task is to provide hands-on experience with:

* Understanding disk structure

* Creating partitions

* Formatting file systems

* Mounting partitions

* Managing storage in both Linux and Windows environments

---

## **Project Architecture**

* Step 1: Understand Disk Partition Types

* Step 2: Disk Partitioning in Ubuntu (MBR using `fdisk`)

* Step 3: Format and Mount Partition

* Step 4: Disk Partitioning in Windows (GPT using Disk Management)

* Step 5: Verify Partitions

---

# **Step By Step Process**

---

## **Step 1: Understanding Partition Types**

### **🔹 MBR (Master Boot Record)**

* Supports up to 4 primary partitions

* Maximum disk size: 2TB

* Older partitioning scheme

* Commonly used in legacy BIOS systems

### **🔹 GPT (GUID Partition Table)**

* Supports more than 4 partitions

* Supports disks larger than 2TB

* More reliable and modern

* Used with UEFI systems

---

# **Part A: Disk Partitioning in Ubuntu (MBR)**

Performed on Ubuntu Server instance in  
 **Amazon Web Services EC2**

---

## **Step 2: Check Available Disks**

lsblk

This displays all available disks and partitions.

---

## **Step 3: Create Partition using fdisk**

Select the disk (example: `/dev/xvdb` or `/dev/sdb`):

sudo fdisk /dev/xvdb

Inside fdisk:

* Press `n` → Create new partition

* Select `p` → Primary

* Choose partition number

* Press Enter for default sector values

* Press `w` → Write changes and exit

---

## **Step 4: Format the Partition**

After creating the partition:

sudo mkfs.ext4 /dev/xvdb1

This formats the partition with EXT4 file system.

---

## **Step 5: Create Mount Point**

sudo mkdir /mnt/mydisk  
---

## **Step 6: Mount the Partition**

sudo mount /dev/xvdb1 /mnt/mydisk

Verify:

df \-h  
---

## **Step 7: Permanent Mount (Optional)**

Edit fstab:

sudo nano /etc/fstab

Add:

/dev/xvdb1  /mnt/mydisk  ext4  defaults  0  0

Save and exit.

---

# **Part B: Disk Partitioning in Windows (GPT)**

Performed using Windows Disk Management Tool.

---

## **Step 1: Open Disk Management**

1. Press **Win \+ R**

2. Type:

diskmgmt.msc

3. Press Enter

---

## **Step 2: Initialize Disk as GPT**

If new disk appears:

* Right-click disk

* Select **Initialize Disk**

* Choose **GPT (GUID Partition Table)**

* Click OK

---

## **Step 3: Create New Volume**

1. Right-click unallocated space

2. Select **New Simple Volume**

3. Click Next

4. Specify volume size

5. Assign drive letter

6. Choose file system (NTFS recommended)

7. Click Finish

---

## **Step 4: Verify Partition**

* Check new drive in **File Explorer**

* Confirm storage allocation

---

# **Verification Commands (Linux)**

lsblk  
sudo fdisk \-l  
df \-h  
---

# **Learning Outcomes**

After completing this task, you will understand:

* Difference between MBR and GPT

* Disk partitioning in Linux using `fdisk`

* Formatting and mounting partitions

* Windows Disk Management usage

* Basic storage administration concepts

