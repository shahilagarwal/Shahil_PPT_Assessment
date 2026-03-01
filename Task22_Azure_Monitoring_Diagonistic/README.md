# **Task 22: Azure Monitoring & Diagnostics (Easy)**

## **Simple Definition**

* Enable monitoring and diagnostics for Azure resources to track performance and health.

## **Objective**

* Learn how to use Azure Monitor

* Collect metrics and logs for resources

* Understand performance tracking and diagnostics in Microsoft Azure

## **Concept Overview**

### **Azure Monitor**

* Centralized monitoring service for Azure resources

* Collects metrics, logs, and diagnostic data

* Supports alerts, dashboards, and insights

### **Key Concepts**

* **Metrics**: Numerical measurements like CPU usage, memory, disk I/O

* **Logs**: Detailed records of events and operations

* **Alerts**: Notifications triggered by metrics or logs

* **Diagnostic Settings**: Enable collection of resource logs

---

## **Step by Step Implementation**

### **Step 1 Open Azure Monitor**

1. Go to **Azure Portal → Monitor**

2. Explore overview dashboard for metrics and alerts

### **Step 2 Enable Diagnostics for a Resource**

1. Open the resource (e.g., VM, Storage Account)

2. Go to **Diagnostic settings → \+ Add diagnostic setting**

3. Select metrics and logs to collect

4. Choose destination (Log Analytics, Storage Account, or Event Hub)

5. Save settings

### **Step 3 View Metrics**

1. Go to **Monitor → Metrics**

2. Select the resource and metric namespace

3. Choose metric to view (e.g., CPU %, Disk Read/Write, Network)

4. Customize chart and time range

### **Step 4 Create Alerts (Optional)**

1. Go to **Monitor → Alerts → \+ Create → Alert Rule**

2. Select **Resource** and metric

3. Set **Condition** (example: CPU \> 70%)

4. Select **Action Group** to notify via email, SMS, or webhook

5. Review and create alert rule

### **Step 5 Review Logs (Optional)**

* Use **Logs → Log Analytics**

* Query collected data using Kusto Query Language (KQL)

* Identify trends, errors, or anomalies

