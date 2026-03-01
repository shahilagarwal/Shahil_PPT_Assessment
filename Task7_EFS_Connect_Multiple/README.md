# **Create EFS and Connect to Multiple Ubuntu Instances**

## **Simple Definition**

* Mount shared storage across multiple EC2 instances using Amazon EFS.

## **Objective**

* Understand shared file systems

* Learn scalable storage architecture

* Connect multiple Ubuntu EC2 instances to a common storage

* Implement distributed storage in Amazon Web Services

## **Concept Overview**

### **Amazon EFS**

* Elastic File System

* Fully managed NFS based file storage

* Can be mounted on multiple EC2 instances simultaneously

* Automatically scales storage up and down

### **NFS**

* Network File System protocol

* Allows file sharing over network

### **Use Case**

* Shared web content

* Application shared storage

* Centralized file storage

## **Step by Step Implementation**

### **Step 1 Create EFS**

* Go to EFS Dashboard

* Click Create file system

* Select VPC

* Select Availability Zones

* Configure security group to allow NFS port 2049

* Click Create

### **Step 2 Configure Security Group**

* Open Security Groups

* Edit inbound rules

* Add rule

* Type NFS

* Port 2049

* Source EC2 security group or VPC CIDR

* Save changes

### **Step 3 Launch Two Ubuntu EC2 Instances**

* Launch two Ubuntu instances in same VPC

* Attach same security group that allows NFS

* Ensure instances are in different Availability Zones for high availability

### **Step 4 Install NFS Client on EC2**

Connect to each Ubuntu instance and run

sudo apt update  
sudo apt install nfs-common \-y

### **Step 5 Mount EFS on Instance**

Create mount directory

sudo mkdir /mnt/efs

Mount using EFS DNS name

sudo mount \-t nfs4 \-o nfsvers=4.1 fs-xxxxxx.efs.region.amazonaws.com:/ /mnt/efs

Replace fs-xxxxxx and region with actual values

### **Step 6 Verify Shared Storage**

On first instance

cd /mnt/efs  
sudo touch sharedfile.txt

On second instance

cd /mnt/efs  
ls

You should see sharedfile.txt

### **Step 7 Make Mount Persistent**

Edit fstab

sudo nano /etc/fstab

Add entry

fs-xxxxxx.efs.region.amazonaws.com:/ /mnt/efs nfs4 defaults,\_netdev 0 0

Save and test

sudo mount \-a

## **Final Outcome**

* EFS created

* Security group configured for NFS

* Multiple Ubuntu instances launched

* EFS mounted successfully

* Shared file accessible from multiple instances

## **Key Learning Points**

* EFS supports multiple EC2 connections

* NFS protocol enables shared storage

* EFS automatically scales

* Useful for distributed applications and shared content systems

