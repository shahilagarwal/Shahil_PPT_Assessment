# **Access S3 from Ubuntu using IAM Roles and Policies**

## **Simple Definition**

* Securely access Amazon S3 from an EC2 instance using an IAM Role instead of access keys.

## **Objective**

* Understand role based authentication

* Avoid hardcoding access keys

* Improve security best practices

* Implement secure access in Amazon Web Services

## **Concept Overview**

### **IAM Role**

* Provides temporary security credentials

* Assigned to EC2 instance

* No need to store access keys manually

### **IAM Policy**

* Defines permissions such as S3 read or write access

* Attached to IAM Role

### **Why Use IAM Role Instead of Access Keys**

* No need to store secret keys in server

* Credentials rotate automatically

* More secure and recommended by AWS

## **Step by Step Implementation**

### **Step 1 Create IAM Role**

* Go to IAM Dashboard

* Click Roles

* Click Create role

* Select Trusted entity type as AWS service

* Select Use case as EC2

* Click Next

### **Step 2 Attach S3 Policy**

* Attach policy such as AmazonS3FullAccess or AmazonS3ReadOnlyAccess

* Click Next

* Enter role name

* Click Create role

### **Step 3 Attach IAM Role to EC2 Instance**

* Go to EC2 Dashboard

* Select running Ubuntu instance

* Click Actions

* Select Security

* Click Modify IAM Role

* Attach newly created role

* Save changes

### **Step 4 Install AWS CLI on Ubuntu**

Connect to EC2 and run

sudo apt update  
sudo apt install awscli \-y

Check version

aws \--version

### **Step 5 Test S3 Access**

List S3 buckets

aws s3 ls

Upload file to S3

echo "Test File" \> test.txt  
aws s3 cp test.txt s3://your-bucket-name/

Download file from S3

aws s3 cp s3://your-bucket-name/test.txt .

## **Verification**

* If commands work without configuring aws configure

* IAM Role is working successfully

* No access keys stored in instance

## **Final Outcome**

* IAM Role created

* S3 policy attached

* Role assigned to EC2

* AWS CLI installed

* S3 accessed securely without access keys

## **Key Learning Points**

* IAM Roles provide temporary credentials

* More secure than using access keys

* Recommended best practice for EC2 to S3 access

* Role based access improves security and management

