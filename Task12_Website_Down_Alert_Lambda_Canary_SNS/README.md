# **Task 12: Website Down Alert using Lambda Canary and SNS**

## **Simple Definition**

* Monitor website uptime and send email alerts when the website becomes unavailable.

## **Objective**

* Understand automated monitoring

* Implement alert notification system

* Learn event driven monitoring architecture

* Improve reliability in Amazon Web Services

## **Concept Overview**

### **CloudWatch Synthetics Canary**

* Continuously checks website endpoint

* Records success and failure metrics

* Runs on scheduled intervals

### **CloudWatch Alarm**

* Monitors Canary failure metric

* Triggers action when threshold is breached

### **SNS**

* Sends email notifications

* Notifies subscribers during failures

## **Step by Step Implementation**

### **Step 1 Create SNS Topic**

* Go to SNS Dashboard

* Click Create topic

* Select Standard type

* Enter topic name

* Create topic

### **Step 2 Create Email Subscription**

* Open created topic

* Click Create subscription

* Select protocol Email

* Enter email address

* Confirm subscription from inbox

### **Step 3 Create Canary**

* Go to CloudWatch

* Click Synthetics

* Click Create Canary

* Choose Heartbeat monitoring blueprint

* Enter website URL

* Set schedule rate 1 minute

* Create new IAM role automatically

* Create Canary

### **Step 4 Create Alarm**

* Open Canary

* Click Create alarm

* Select metric Failed

* Set condition greater than or equal to 1

* Choose SNS topic for notification

* Create alarm

### **Step 5 Test the Setup**

* Stop web server if hosted on EC2

* Wait for Canary to detect failure

* Verify email notification received

* Start web server again

