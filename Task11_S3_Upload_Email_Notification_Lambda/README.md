# **S3 Upload Email Notification Lambda and SNS**

## **Simple Definition**

* Trigger an email notification automatically when a file is uploaded to an Amazon S3 bucket.

## **Objective**

* Understand event driven architecture

* Integrate S3, Lambda and SNS

* Automate email notifications in Amazon Web Services

## **Step by Step Implementation**

### **Step 1 Create S3 Bucket**

* Go to S3 Dashboard

* Click Create bucket

* Enter unique bucket name

* Select region

* Create bucket

### **Step 2 Create SNS Topic**

* Go to SNS Dashboard

* Click Create topic

* Select Standard type

* Enter topic name

* Create topic

### **Step 3 Create Email Subscription**

* Open SNS topic

* Click Create subscription

* Select protocol Email

* Enter email address

* Confirm subscription from email inbox

### **Step 4 Create IAM Role for Lambda**

* Go to IAM

* Create role for Lambda

* Attach policies AmazonS3ReadOnlyAccess and AmazonSNSFullAccess

* Create role

### **Step 5 Create Lambda Function**

* Go to Lambda Dashboard

* Click Create function

* Select Author from scratch

* Choose Python runtime

* Attach created IAM role

* Create function

Add code

import json  
import boto3

sns \= boto3.client('sns')

def lambda\_handler(event, context):  
   sns.publish(  
       TopicArn='arn:aws:sns:region:account-id:topic-name',  
       Message='New file uploaded to S3 bucket',  
       Subject='S3 Upload Notification'  
   )  
   return {  
       'statusCode': 200  
   }

Replace TopicArn with actual SNS topic ARN and deploy.

### **Step 6 Configure S3 Trigger**

* Open Lambda function

* Click Add trigger

* Select S3

* Choose bucket

* Select event type Object Created

* Add trigger

### **Step 7 Test**

* Upload file to S3 bucket

* Check email for notification

