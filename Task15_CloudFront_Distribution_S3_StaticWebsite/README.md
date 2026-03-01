# **Task 15: CloudFront Distribution for S3 Static Website**

## **Simple Definition**

* Use Content Delivery Network (CDN) to deliver S3 static website faster to users globally.

## **Objective**

* Improve website performance and latency

* Learn global content distribution

* Implement CloudFront integration with S3 in Amazon Web Services

## **Concept Overview**

### **Amazon CloudFront**

* CDN service that caches content at edge locations

* Reduces latency for global users

* Integrates with S3, API Gateway, or custom origins

### **S3 Static Website**

* Stores HTML, CSS, JS, images

* Serves content publicly or privately

* Origin for CloudFront distribution

### **Benefits**

* Faster content delivery

* Reduced load on origin S3 bucket

* SSL and HTTPS support

* Access logging and analytics

## **Step by Step Implementation**

### **Step 1 Prepare S3 Bucket**

* Ensure S3 bucket has website hosting enabled

* Upload all static website files

* Set public access or configure bucket policy for CloudFront

### **Step 2 Create CloudFront Distribution**

* Go to CloudFront Dashboard

* Click Create Distribution → Web

* Select S3 bucket as origin

* Set Default Root Object (index.html)

* Enable or customize caching settings

* Enable SSL (Default CloudFront certificate)

* Create distribution

### **Step 3 Configure DNS (Optional)**

* Create CNAME in Route 53 or DNS provider

* Point to CloudFront domain name

### **Step 4 Test Website**

* Open CloudFront domain in browser

* Verify website loads with improved speed

* Test HTTPS if enabled  
