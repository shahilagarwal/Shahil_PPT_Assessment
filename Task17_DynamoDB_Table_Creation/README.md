# **Task 17: DynamoDB Table Creation (Basic)**

## **Simple Definition**

* Create a serverless NoSQL table using Amazon DynamoDB and insert sample data.

  ## **Objective**

* Learn basics of NoSQL database

* Understand key concepts like partition key and sort key

* Perform basic operations like insert and query

* Explore serverless database features in Amazon Web Services

  ## **Concept Overview**

  ### **Amazon DynamoDB**

* Fully managed NoSQL database

* Serverless, scales automatically

* Stores data in tables with key-value structure

* Supports high throughput and low latency

  ### **Key Concepts**

* Table: Container for items

* Item: Individual record (like a row in SQL)

* Partition Key: Unique identifier for each item

* Sort Key (optional): Allows sorting items under the same partition

* Attributes: Columns or fields of an item

  ## **Step by Step Implementation**

  ### **Step 1 Create DynamoDB Table**

* Go to **DynamoDB Dashboard → Tables → Create table**

* Enter **Table name** (example: `Students`)

* Enter **Partition key** (example: `StudentID` → Number)

* Optionally, add **Sort key** (example: `CourseID`)

* Leave other settings default (or enable on-demand capacity for practice)

* Click **Create table**

  ### **Step 2 Insert Sample Items**

* Open table → **Explore items → Create item**

* Add fields and values (example):

  {  
   "StudentID": 1,  
   "Name": "Vivek",  
   "Age": 22,  
   "Course": "IT"  
  }  
* Add another item:

  {  
   "StudentID": 2,  
   "Name": "Ramu",  
   "Age": 23,  
   "Course": "IT"  
  }

  ### **Step 3 Query Table**

* Open **Explore items → Query**

* Use Partition Key `StudentID = 1`

* Verify returned item matches expected record

  ### **Step 4 Update Item**

* Select item → Edit → Change attribute (example: `Age = 24`)

* Save changes

  ### **Step 5 Delete Item**

* Select item → Actions → Delete item

  ## **Final Outcome**

* DynamoDB table created

* Items inserted and retrieved successfully

* Basic CRUD operations performed  
* 