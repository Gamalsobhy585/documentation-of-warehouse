---
title: Authorization & Security
nav_order: 9
---

# Authorization & Security

The **Warehouse module** follows a **Role-Based Access Control (RBAC)** system to ensure that every action within the ERP is securely restricted to **authorized users only**.

Each **permission** defines a specific action (e.g., viewing, creating, editing, or deleting data), and every **role** is composed of a defined set of permissions.  
Users inherit permissions through their **assigned roles**, ensuring clear separation of access levels across the organization.

---

## 🎯 Purpose

RBAC guarantees that users can only perform actions relevant to their responsibilities, minimizing the risk of unauthorized access or data modification.  
It also provides clear audit trails for accountability.

---

## 🧾 Permission-Based Access

Every controller action and page in the Warehouse module is protected by a corresponding **permission key**.

Before executing any action, the system checks whether the **authenticated user** has the required permission.

Example (Laravel controller check):

```php
checkUserIsAuthorized('warehouse-delivery-items-index');
