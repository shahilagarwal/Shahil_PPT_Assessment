# **Task 16: RDS Database \+ SQL Workbench Connection and Queries**

## **Simple Definition**

* Create a managed relational database and connect using SQL Workbench to execute queries.

  ## **Objective**

* Understand Amazon RDS and managed database services

* Learn how to connect to RDS securely

* Execute basic SQL queries for database operations

* Implement scalable and managed database in Amazon Web Services

  ## **Concept Overview**

  ### **Amazon RDS**

* Managed relational database service

* Supports MySQL, PostgreSQL, MariaDB, SQL Server, and Oracle

* Handles backups, patching, and scaling automatically

  ### **SQL Workbench**

* SQL client for connecting to relational databases

* Allows executing queries and managing data

  ### **Key Concepts**

* DB Instance: Individual database server

* Subnet Group: Determines which VPC subnets the DB resides in

* Security Group: Controls access to DB instance

* Endpoint: Hostname for connecting to database

  ## **Step by Step Implementation**

  ### **Step 1 Launch RDS Instance**

* Go to **RDS Dashboard → Databases → Create database**

* Select engine (MySQL/PostgreSQL recommended for practice)

* Choose **Standard Create**

* Set DB instance identifier and master username/password

* Configure **VPC, subnet group, and public accessibility** (enable if connecting from outside VPC)

* Configure storage and instance type (for practice, small size is sufficient)

* Create database

  ### **Step 2 Configure Security Group**

* Open EC2 Security Groups

* Edit inbound rules to allow port **3306** (MySQL) or **5432** (PostgreSQL)

* Add source as your IP address

  ### **Step 3 Retrieve Endpoint**

* Open RDS instance details

* Copy **Endpoint** and **Port**

  ### **Step 4 Connect Using SQL Workbench**

* Open SQL Workbench

* Create new connection profile

* Enter RDS endpoint, port, database name, username, and password

* Test connection → Save and connect

  ### **Step 5 Execute Basic SQL Queries**

* Create a table:

  CREATE TABLE students (  
     id INT PRIMARY KEY,  
     name VARCHAR(50),  
     age INT  
  );  
* Insert data:

  INSERT INTO students (id, name, age) VALUES (1, 'Vivek', 22);  
  INSERT INTO students (id, name, age) VALUES (2, 'Ramu', 23);  
* Retrieve data:

  SELECT \* FROM students;  
* Update data:

  UPDATE students SET age \= 24 WHERE id \= 1;  
* Delete data:

  DELETE FROM students WHERE id \= 2;

  ### **Step 6 Verify Changes**

* Execute `SELECT * FROM students;`

* Verify all insert, update, and delete operations  
* 