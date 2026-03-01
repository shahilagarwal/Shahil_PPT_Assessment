# **VPC 3 Tier Architecture**

## **Simple Definition**

* Design a three tier network architecture with public and private subnets inside a VPC.

## **Objective**

* Understand VPC networking fundamentals

* Configure Internet Gateway and NAT Gateway

* Implement public and private subnet isolation

* Learn Network ACL and Security Group concepts

* Configure SSH tunneling for secure access

* Build secure architecture in Amazon Web Services

## **Concept Overview**

### **VPC**

* Virtual Private Cloud

* Isolated virtual network inside AWS

* Allows control over IP range, subnets and routing

### **Three Tier Architecture**

* Presentation Tier in Public Subnet

* Application Tier in Private Subnet

* Database Tier in Private Subnet

* Improves security and scalability

### **Internet Gateway**

* Allows public subnet to access internet

* Required for public facing resources

### **NAT Gateway**

* Allows private subnet instances to access internet

* Prevents inbound internet access to private instances

### **Network ACL**

* Stateless firewall at subnet level

* Controls inbound and outbound traffic

### **Security Group**

* Stateful firewall at instance level

* Controls instance level traffic

### **SSH Tunneling**

* Securely access private instances using bastion host

* Used to manage private resources

## **Step by Step Implementation**

### **Step 1 Create VPC**

* Go to VPC Dashboard

* Click Create VPC

* Enter VPC name

* Enter IPv4 CIDR block such as 10.0.0.0/16

* Create VPC

### **Step 2 Create Subnets**

* Create Public Subnet in Availability Zone 1

* CIDR example 10.0.1.0/24

* Enable Auto assign public IP

* Create Private Subnet for Application Tier

* CIDR example 10.0.2.0/24

* Create Private Subnet for Database Tier

* CIDR example 10.0.3.0/24

### **Step 3 Create Internet Gateway**

* Go to Internet Gateways

* Click Create Internet Gateway

* Attach to created VPC

### **Step 4 Configure Route Table for Public Subnet**

* Create Public Route Table

* Add route 0.0.0.0/0 to Internet Gateway

* Associate Public Subnet

### **Step 5 Create NAT Gateway**

* Allocate Elastic IP

* Create NAT Gateway in Public Subnet

* Attach Elastic IP

### **Step 6 Configure Route Table for Private Subnets**

* Create Private Route Table

* Add route 0.0.0.0/0 to NAT Gateway

* Associate Application and Database subnets

### **Step 7 Launch EC2 Instances**

* Launch Bastion Host in Public Subnet

* Launch Application Server in Private Subnet

* Launch Database Server in Private Subnet

### **Step 8 Configure Security Groups**

* Bastion Host allow SSH from your IP

* Application Server allow SSH only from Bastion

* Database allow access only from Application Server

### **Step 9 Configure SSH Tunneling**

From local machine connect to Bastion

ssh \-i key.pem ec2-user@bastion-public-ip

Connect to private instance through Bastion

ssh \-i key.pem private-user@private-ip

Or use SSH tunneling

ssh \-i key.pem \-L 3306:private-db-ip:3306 ec2-user@bastion-public-ip

### **Step 10 Verify Internet Access**

* Public instance should access internet directly

* Private instances should access internet through NAT

* Private instances should not have public IP

## **Architecture Flow**

* User connects to Public Subnet

* Public Subnet routes traffic through Internet Gateway

* Private Subnet routes traffic through NAT Gateway

* Database isolated in private network

## **Final Outcome**

* Custom VPC created

* Public and Private subnets configured

* Internet Gateway attached

* NAT Gateway configured

* Route tables properly associated

* Security Groups configured

* SSH tunneling working

* Three tier architecture successfully implemented

## **Key Learning Points**

* VPC provides network isolation

* Public subnet exposes resources to internet

* Private subnet improves security

* NAT Gateway enables outbound internet for private instances

* Security Groups and NACL provide layered security

* Three tier architecture improves scalability and protection

