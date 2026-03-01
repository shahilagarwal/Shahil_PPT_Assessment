# **Task 14: CloudWatch Alarm 70% CPU → Auto Stop \+ Email**

## **Simple Definition**

* Monitor EC2 CPU usage and automatically stop instance while sending email alert when CPU exceeds 70%.

## **Objective**

* Learn automated monitoring

* Implement CloudWatch alarm with actions

* Combine EC2 control and notifications in Amazon Web Services

## **Concept Overview**

### **CloudWatch Alarm**

* Monitors metrics such as CPU utilization

* Triggers actions when threshold is breached

### **EC2 Stop Action**

* Stops instance automatically to prevent overuse or cost

* Can be integrated with alarm actions

### **SNS**

* Sends email notifications

* Notifies subscribed users in real-time

## **Step by Step Implementation**

### **Step 1 Create SNS Topic**

* Go to SNS Dashboard

* Click Create topic

* Select Standard type

* Enter topic name

* Create topic

### **Step 2 Create Email Subscription**

* Open topic

* Click Create subscription

* Protocol select Email

* Enter email address

* Confirm subscription from inbox

### **Step 3 Create CloudWatch Alarm**

* Go to CloudWatch

* Click Alarms → Create Alarm

* Select EC2 metric CPUUtilization

* Select instance

* Set threshold 70%

* Select period (e.g., 1 minute)

* Select Evaluation period 1

* Add actions:

  * Stop EC2 instance

  * Send notification to SNS topic

* Create alarm

### **Step 4 Test the Setup**

* Run CPU stress on EC2 instance (optional for testing)

* Wait for alarm to trigger

* Verify EC2 instance stops

* Check email notification received

## **Final Outcome**

* CloudWatch alarm created

* EC2 stop action configured

* SNS email notifications enabled

* CPU threshold breach triggers automatic stop and alert

