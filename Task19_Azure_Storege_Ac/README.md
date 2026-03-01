# **Task 19: Azure Storage Account (Blob, File, Table)**

## **Simple Definition**

* Create an Azure Storage Account and explore Blob, File, and Table storage services.

## **Objective**

* Learn different storage types in Azure

* Upload and manage sample data

* Understand scalable and secure storage options in Microsoft Azure

## **Concept Overview**

### **Azure Storage Account**

* Provides cloud storage for objects, files, and NoSQL tables

* Supports Blob, File, Table, and Queue storage

* Managed, scalable, and secure

### **Storage Types**

**Blob Storage**

* Stores unstructured data like images, videos, documents

* Can be accessed via HTTP/HTTPS

**File Storage**

* Provides SMB or NFS file shares

* Allows mounting file system on Windows or Linux

**Table Storage**

* NoSQL key-value store

* Stores structured, non-relational data

---

## **Step by Step Implementation**

### **Step 1 Create Storage Account**

1. Go to **Azure Portal → Storage Accounts → Create**

2. Select **Subscription** and **Resource Group**

3. Enter **Storage Account Name** (unique)

4. Choose **Region**

5. Select **Performance**: Standard

6. Select **Replication**: LRS (for practice)

7. Click **Review \+ Create → Create**

### **Step 2 Explore Blob Storage**

1. Open created storage account → **Containers → \+ Container**

2. Enter container name → Set **Public access level**

3. Upload sample files (images, HTML, etc.)

4. Test file access via generated URL

### **Step 3 Explore File Storage**

1. Open storage account → **File shares → \+ File share**

2. Enter file share name → Set quota (optional)

3. Upload sample files

4. Mount file share on local machine (Windows: Map network drive, Linux: `mount -t cifs`)

### **Step 4 Explore Table Storage**

1. Open storage account → **Tables → \+ Table**

2. Enter table name (example: `Students`)

3. Insert sample items:

   * PartitionKey: `Dept1`

   * RowKey: `1`

   * Add attributes: `Name = Vivek`, `Age = 22`

4. Add another item with RowKey `2`

### **Step 5 Verify Data Access**

* Blob: Access via URL

* File: Mount or download

* Table: Query or browse items

