# **Create IAM Users and Groups**

## **Simple Definition**

* Manage users and permissions using Identity and Access Management.

## **Objective**

* Understand access control mechanism

* Learn how to assign permissions securely

* Implement role based access control

* Improve security management in Amazon Web Services

## **Concept Overview**

### **IAM**

* Identity and Access Management service

* Controls who can access AWS resources

* Defines permissions using policies

### **IAM User**

* Represents a person or application

* Has login credentials

* Can be assigned permissions directly or through groups

### **IAM Group**

* Collection of IAM users

* Permissions are attached to group

* All users in group inherit same permissions

### **IAM Policy**

* JSON document defining permissions

* Specifies allowed or denied actions

* Can be AWS managed or custom

## **Step by Step Implementation**

### **Step 1 Open IAM Dashboard**

* Go to IAM service in AWS Console

* Open Users section

### **Step 2 Create IAM Group**

* Click User groups

* Click Create group

* Enter group name

* Attach required policy such as AmazonS3FullAccess or AmazonEC2ReadOnlyAccess

* Click Create group

### **Step 3 Create IAM User**

* Go to Users

* Click Create user

* Enter user name

* Select access type

* For console access enable password

* For programmatic access enable access key

* Click Next

### **Step 4 Add User to Group**

* Select previously created group

* Review and create user

### **Step 5 Download Credentials**

* Download access key and secret key if programmatic access enabled

* Save credentials securely

### **Step 6 Verify Permissions**

* Logout from root account

* Login using IAM user credentials

* Access allowed services

* Verify restricted services cannot be accessed

## **Final Outcome**

* IAM group created

* Policy attached to group

* IAM user created

* User added to group

* Permissions successfully applied

## **Key Learning Points**

* IAM improves security management

* Groups simplify permission assignment

* Policies define allowed actions

* Principle of least privilege should be followed

