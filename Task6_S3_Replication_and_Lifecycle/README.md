# **S3 Replication and Lifecycle Policy**

## **Simple Definition**

* Configure replication and lifecycle rules in Amazon S3 to automate backup and optimize storage cost.

## **Objective**

* Understand S3 replication concept

* Implement cross bucket backup strategy

* Learn lifecycle rules for cost optimization

* Manage storage efficiently in Amazon Web Services

## **Concept Overview**

### **Amazon S3 Replication**

* Automatically copies objects from one bucket to another

* Works across different regions or within same region

* Requires versioning to be enabled

* Helps in backup and disaster recovery

### **Versioning**

* Keeps multiple versions of an object

* Prevents accidental deletion

* Required for replication

### **Lifecycle Policy**

* Automatically moves objects to cheaper storage classes

* Can delete old versions after defined period

* Reduces storage cost

## **Step by Step Implementation**

### **Step 1 Create Source and Destination Buckets**

* Go to S3 Dashboard

* Create Source bucket

* Create Destination bucket

* Ensure both buckets are in required regions

### **Step 2 Enable Versioning**

* Open Source bucket

* Go to Properties

* Enable Versioning

* Save changes

* Repeat same for Destination bucket

### **Step 3 Configure Replication Rule**

* Open Source bucket

* Go to Management tab

* Click Create Replication Rule

* Enter rule name

* Select Apply to all objects

* Choose Destination bucket

* Create or select IAM role

* Save rule

### **Step 4 Verify Replication**

* Upload a file in Source bucket

* Open Destination bucket

* Verify file is automatically copied

### **Step 5 Configure Lifecycle Policy**

* Open Source bucket

* Go to Management tab

* Click Create Lifecycle Rule

* Enter rule name

* Apply to all objects

* Choose Transition action

* Move objects to Standard IA after specific days

* Move objects to Glacier after specific days

* Optionally set Expiration to delete objects after certain days

* Save rule

### **Step 6 Test Lifecycle Policy**

* Upload test file

* Wait for lifecycle transition period

* Verify storage class change in object properties

## **Final Outcome**

* Source and Destination buckets created

* Versioning enabled

* Replication rule configured

* Objects replicated automatically

* Lifecycle policy configured

* Cost optimization and backup strategy implemented

## **Key Learning Points**

* Versioning is mandatory for replication

* Replication improves data durability and disaster recovery

* Lifecycle rules reduce storage cost

* S3 automates backup and storage management

