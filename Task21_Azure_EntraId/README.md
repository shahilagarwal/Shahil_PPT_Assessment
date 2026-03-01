# **Task 21: Entra ID (Users, Roles, Basic Identity Management)**

## **Simple Definition**

* Manage users, groups, and roles in Azure Entra ID (formerly Azure Active Directory) for identity and access management.

## **Objective**

* Learn how to create and manage users

* Assign roles and control access

* Understand basic identity management in Microsoft Azure

## **Concept Overview**

### **Azure Entra ID**

* Cloud-based identity and access management service

* Centralizes authentication and authorization

* Supports role-based access control (RBAC)

### **Key Concepts**

* **User**: Individual identity for login

* **Group**: Collection of users for easier management

* **Role**: Defines permissions for resources

* **RBAC**: Role-Based Access Control, assigns roles to users or groups

---

## **Step by Step Implementation**

### **Step 1 Create a User**

1. Go to **Azure Portal → Entra ID → Users → \+ New user**

2. Enter **User Name** and **Name**

3. Select **Identity Type**: Cloud user

4. Assign **Password** (auto-generated or custom)

5. Click **Create**

### **Step 2 Create a Group (Optional)**

1. Go to **Entra ID → Groups → \+ New group**

2. Enter **Group Name** (example: `Developers`)

3. Select **Membership Type**: Assigned

4. Add users to group

5. Click **Create**

### **Step 3 Assign Roles**

1. Go to **Entra ID → Roles and administrators**

2. Select a role (example: **User Administrator**)

3. Click **Add assignment → Select users or groups**

4. Choose the desired user/group

5. Click **Assign**

### **Step 4 Verify Role and Access**

* Check user or group → **Assigned Roles**

* Confirm user can access resources per assigned role

### **Step 5 Test Login (Optional)**

* Sign in with newly created user credentials

* Verify access to Azure portal or assigned resources

