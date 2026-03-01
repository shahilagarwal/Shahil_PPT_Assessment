# **Task 18: Azure Virtual Machine (Easy Task)**

## **Simple Definition**

* Launch and configure a basic Azure Virtual Machine (VM) for remote access and basic usage.

## **Objective**

* Understand Azure compute fundamentals

* Learn VM creation and access

* Explore RDP/SSH connectivity in Microsoft Azure

## **Concept Overview**

### **Azure Virtual Machine**

* Provides scalable, on-demand compute resources

* Supports Windows and Linux operating systems

* Accessible via **RDP** (Windows) or **SSH** (Linux)

* Integrates with storage, networking, and security services

### **Key Concepts**

* **VM Size**: Determines CPU, RAM, and storage

* **Resource Group**: Logical container for resources

* **Public IP**: Required for remote access

* **Network Security Group (NSG)**: Controls inbound/outbound traffic

---

## **Step by Step Implementation**

### **Step 1 Create Resource Group**

1. Go to **Azure Portal → Resource Groups → \+ Create**

2. Enter **Resource Group Name** (example: `MyVM-RG`)

3. Select **Region**

4. Click **Review \+ Create → Create**

### **Step 2 Create Virtual Machine**

1. Go to **Virtual Machines → \+ Create → Azure Virtual Machine**

2. Select **Subscription** and **Resource Group**

3. Enter **VM Name**

4. Select **Region**

5. Choose **Image** (Windows 11 / Ubuntu 22.04 LTS for practice)

6. Select **VM Size** (e.g., B1s for small test VM)

7. Configure **Authentication Type**:

   * **Password** (Windows)

   * **SSH Public Key** (Linux)

8. Enable **Public IP**

9. Create **Inbound Port Rules**:

   * RDP (3389) for Windows

   * SSH (22) for Linux

10. Click **Review \+ Create → Create**

### **Step 3 Connect to VM**

**Windows VM (RDP)**

1. Download `.rdp` file from Azure portal

2. Open Remote Desktop client

3. Enter username and password

4. Connect to VM

**Linux VM (SSH)**

1. Open terminal

2. Run command:

ssh azureuser@\<Public-IP\>

3. Enter SSH private key if using key authentication

### **Step 4 Perform Basic Configuration**

* Update OS and install packages

* For Linux: `sudo apt update && sudo apt upgrade`

* For Windows: Install applications via GUI or PowerShell

### **Step 5 Optional – Stop/Start VM**

* Go to VM → **Stop** to save costs

* **Start** when needed

---

## **Final Outcome**

* Azure VM created and running

* Accessible via RDP (Windows) or SSH (Linux)

* Basic OS configuration completed

* Public IP allows remote access

