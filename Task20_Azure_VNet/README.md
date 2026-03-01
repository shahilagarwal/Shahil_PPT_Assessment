# **Task 20: Azure VNet (Basic Networking Practical)**

## **Simple Definition**

* Configure a virtual network (VNet) with subnets and security rules in Azure to enable controlled communication.

## **Objective**

* Understand basic cloud networking concepts

* Learn to create VNet, subnets, and NSG rules

* Enable secure communication between resources in Microsoft Azure

## **Concept Overview**

### **Azure Virtual Network (VNet)**

* Logical isolation of network in Azure

* Enables resources to communicate securely

* Supports subnets, IP addressing, routing, and security

### **Subnets**

* Segment VNet into smaller networks

* Assign IP ranges

* Improve traffic management and security

### **Network Security Group (NSG)**

* Controls inbound and outbound traffic

* Can attach to subnet or individual VM

* Enables firewall-like rules for resources

---

## **Step by Step Implementation**

### **Step 1 Create Resource Group**

1. Go to **Azure Portal → Resource Groups → \+ Create**

2. Enter **Resource Group Name** (example: `MyVNet-RG`)

3. Select **Region**

4. Click **Review \+ Create → Create**

### **Step 2 Create Virtual Network**

1. Go to **Virtual Networks → \+ Create**

2. Select **Subscription** and **Resource Group**

3. Enter **VNet Name** (example: `MyVNet`)

4. Choose **Region**

5. Set **Address Space** (example: `10.0.0.0/16`)

6. Click **Next → Subnets**

### **Step 3 Create Subnets**

1. Add subnet (example: `Subnet1`)

2. Set **Subnet Address Range** (example: `10.0.1.0/24`)

3. Optionally add another subnet (`Subnet2`)

4. Click **Review \+ Create → Create**

### **Step 4 Configure Network Security Group (NSG)**

1. Go to **NSGs → \+ Create**

2. Enter **NSG Name** (example: `MyNSG`)

3. Select **Resource Group** and **Region**

4. Create NSG

#### **Add Inbound Rules**

* Allow SSH (Port 22\) for Linux VM

* Allow RDP (Port 3389\) for Windows VM

* Allow HTTP (Port 80\) or HTTPS (Port 443\) if needed

#### **Add Outbound Rules (optional)**

* Allow Internet traffic for updates or external communication

### **Step 5 Associate NSG with Subnet**

1. Open NSG → **Subnet associations → Associate**

2. Select VNet and desired subnet

### **Step 6 Deploy VM into VNet (Optional)**

* Go to **Virtual Machines → \+ Create**

* Select the previously created VNet and subnet

* Assign NSG for secure access

