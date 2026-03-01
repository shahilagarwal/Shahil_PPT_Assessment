# **Task 24: SLA, Service Lifecycle & Subscription Management (Easy)**

## **Simple Definition**

* Explore Service Level Agreements (SLA), Azure subscriptions, and service lifecycle concepts for governance and planning.

## **Objective**

* Understand service availability commitments (SLA)

* Manage subscriptions and access

* Learn service lifecycle planning in Microsoft Azure

## **Concept Overview**

### **Service Level Agreement (SLA)**

* Defines uptime and performance guarantees of Azure services

* Helps plan critical workloads based on reliability requirements

### **Subscription**

* Logical container for billing, resources, and access management

* Allows multiple subscriptions under one account for separation of environments

### **Service Lifecycle**

* Azure services go through stages: Preview → General Availability → Deprecated

* Understanding lifecycle ensures compatibility and planning

---

## **Step by Step Implementation**

### **Step 1 Review SLA Information**

1. Go to **Azure Portal → Help \+ Support → SLA**

2. Select service (example: **Virtual Machines, Storage, SQL Database**)

3. Review SLA % uptime and terms

4. Note any regional or configuration dependencies

### **Step 2 Manage Subscriptions**

1. Go to **Azure Portal → Subscriptions**

2. View all subscriptions under your account

3. Create new subscription (if allowed) for testing or separate projects

4. Assign roles and access using **Role-Based Access Control (RBAC)**

5. Monitor billing and usage per subscription

### **Step 3 Understand Service Lifecycle**

1. Check **Azure Updates → Service Announcements**

2. Identify which services are in **Preview, GA (General Availability), or Deprecated**

3. Plan deployments using supported GA services

4. Avoid using deprecated services for production workloads

