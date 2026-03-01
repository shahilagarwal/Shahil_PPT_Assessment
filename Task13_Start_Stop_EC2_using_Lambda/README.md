# **Task 13: Start/Stop EC2 using Lambda \+ API Gateway**

## **Simple Definition**

* Automate starting and stopping EC2 instances using an API trigger.

## **Objective**

* Learn serverless automation

* Control EC2 without manual console access

* Understand API-based infrastructure management in Amazon Web Services

## **Concept Overview**

### **AWS Lambda**

* Executes backend logic without managing servers

* Uses Python/Node.js to start or stop EC2 instances

* Requires IAM role with EC2 permissions

### **API Gateway**

* Creates HTTP endpoint

* Triggers Lambda function when API is called

* Enables remote infrastructure control

### **EC2**

* Target instance to start or stop

* Action performed through Lambda automation

## **Step by Step Implementation**

### **Step 1 Create IAM Role**

* Go to IAM

* Create new role for Lambda

* Attach policy: AmazonEC2FullAccess (for lab/demo)

* Complete role creation

### **Step 2 Create Lambda Function**

* Go to Lambda

* Click Create function

* Choose Author from scratch

* Select runtime (Python recommended)

* Attach created IAM role

* Create function

* Add code to start/stop EC2 instance

* Replace with your EC2 Instance ID

* Deploy function

### **Step 3 Test Lambda**

* Create test event

* Invoke function

* Verify EC2 instance state changes

### **Step 4 Create API Gateway**

* Go to API Gateway

* Create HTTP API

* Add integration with Lambda function

* Configure route (example: /start or /stop)

* Deploy API

### **Step 5 Test API Endpoint**

* Copy generated Invoke URL

* Paste in browser or use Postman

* Verify EC2 instance starts or stops

## **Final Outcome**

* Lambda function created

* API endpoint configured

* EC2 instance controlled via API

* Automation without manual login

