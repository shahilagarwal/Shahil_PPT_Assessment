# **Static Website Hosting in S3**

## **Simple Definition**

* Host a static website using an Amazon S3 bucket.

## **Objective**

* Understand serverless website hosting

* Learn how to configure S3 for public access

* Deploy static files without EC2 server

* Implement static hosting in Amazon Web Services

## **Concept Overview**

### **Amazon S3**

* Object storage service

* Stores files such as HTML, CSS, JS, images

* Highly durable and scalable

### **Static Website Hosting**

* Hosting HTML, CSS and JavaScript files

* No backend server required

* Accessible through S3 website endpoint

### **Serverless Hosting**

* No EC2 instance required

* No operating system management

* Pay only for storage and data transfer

## **Step by Step Implementation**

### **Step 1 Create S3 Bucket**

* Go to S3 Dashboard

* Click Create Bucket

* Enter unique bucket name

* Select Region

* Disable Block all public access

* Acknowledge warning

* Click Create Bucket

### **Step 2 Enable Static Website Hosting**

* Open the created bucket

* Go to Properties tab

* Scroll to Static website hosting

* Click Edit

* Enable Static website hosting

* Select Host a static website

* Enter index document name index.html

* Enter error document name error.html if available

* Save changes

### **Step 3 Upload Website Files**

* Open bucket

* Click Upload

* Add all static website files

* Upload HTML, CSS, JS, images

* Click Upload

### **Step 4 Configure Bucket Policy for Public Access**

* Go to Permissions tab

* Open Bucket Policy

* Add policy to allow public read access

Example Policy

{  
 "Version": "2012-10-17",  
 "Statement": \[  
   {  
     "Sid": "PublicReadGetObject",  
     "Effect": "Allow",  
     "Principal": "\*",  
     "Action": "s3:GetObject",  
     "Resource": "arn:aws:s3:::your-bucket-name/\*"  
   }  
 \]  
}

* Replace your-bucket-name with actual bucket name

* Save policy

### **Step 5 Access Website**

* Go to Properties tab

* Copy Bucket website endpoint

* Open endpoint URL in browser

* Verify website loads successfully

## **Final Outcome**

* S3 bucket created

* Static website hosting enabled

* Website files uploaded

* Public access configured

* Website accessible through S3 endpoint

## **Key Learning Points**

* S3 can host static websites without EC2

* No server management required

* Bucket policy controls public access

* Serverless hosting reduces cost and maintenance

