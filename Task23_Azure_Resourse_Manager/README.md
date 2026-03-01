# **Task 23: Azure Resource Manager & Cost Management (Easy)**

## **Simple Definition**

* Use Azure Resource Manager (ARM) to organize resources and track costs for budgeting and management.

## **Objective**

* Learn how to create and manage resource groups

* Understand ARM for structured resource deployment

* Track and analyze costs for Azure resources in Microsoft Azure

## **Concept Overview**

### **Azure Resource Manager (ARM)**

* Framework to deploy, manage, and organize Azure resources

* Uses **Resource Groups** as logical containers

* Enables template-based deployments and consistent management

### **Resource Group**

* Logical container for related Azure resources

* Simplifies management, monitoring, and access control

* Allows applying tags for billing or environment tracking

### **Cost Management**

* Tracks usage and spending

* Provides dashboards, budgets, and alerts

* Helps optimize cloud costs

---

## **Step by Step Implementation**

### **Step 1 Create a Resource Group**

1. Go to **Azure Portal → Resource Groups → \+ Create**

2. Enter **Resource Group Name** (example: `MyResourceGroup`)

3. Select **Region**

4. Click **Review \+ Create → Create**

### **Step 2 Deploy Resources into Resource Group**

1. While creating any resource (VM, Storage, VNet, etc.), select the created resource group

2. Grouping ensures easier management and billing

### **Step 3 View Cost Analysis**

1. Go to **Cost Management \+ Billing → Cost Management → Cost analysis**

2. Select **Scope**: choose your subscription or resource group

3. View charts for:

   * Monthly spend

   * Daily/weekly usage

   * Costs by resource type

### **Step 4 Set Budget and Alerts (Optional)**

1. Go to **Cost Management → Budgets → \+ Add**

2. Select **Scope** and define **Budget amount**

3. Configure **Alerts** when spending approaches or exceeds budget

4. Save budget

### **Step 5 Tag Resources (Optional)**

* Assign tags like `Environment=Test` or `Project=Demo`

* Tags help filter costs and manage billing by project or team

