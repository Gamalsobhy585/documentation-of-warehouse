---
title: Database Schema & ERD
nav_order: 6
---

# Database Schema & ERD

The **Warehouse module** relies on a **relational MySQL database** designed to maintain **data integrity** and support **modular scalability**.

Each entity — such as `Stock`, `Substock`, `Item`, `Package`, `Goods Receipt`, and `Delivery` — has its own dedicated table with clearly defined relationships to other entities.

---

## 🧾 Overview

All tables in the Warehouse database:

- Use **UUIDs** as primary identifiers for global uniqueness.  
- Include **timestamps** (`created_at`, `updated_at`, `deleted_at`) for lifecycle tracking.  
- Enforce **foreign key constraints** to preserve referential integrity between entities.  
- Follow a consistent **naming convention**, where every table is prefixed with `warehouse_` (e.g., `warehouse_stocks`, `warehouse_items`, `warehouse_goods_receipts`) to maintain clear module separation and easy navigation.

---

## ⚙️ Key Design Principles

- **Normalization** — The schema follows **Third Normal Form (3NF)** to minimize redundancy.  
- **Relationships** — Uses one-to-many and many-to-many relationships between key entities.  
- **Auditability** — Each table includes `created_by`, `updated_by`, and `deleted_by` fields for full traceability.  
- **Soft Deletes** — Implemented via the `deleted_at` column for logical deletion instead of physical removal.  
- **Multilingual Fields** — Some master data tables (e.g., *Items*, *Categories*) include both `name_en` and `name_ar` fields.

---

## 🗺️ ERD

The Entity Relationship Diagram (ERD) visually represents how all entities are connected within the Warehouse module.

👉 **See full ERD diagram [here](https://drive.google.com/file/d/1CqhVKmQy0yR92CHvDiwyNdJ8Qpt6xRKI/view?usp=sharing){:target="_blank"}**

> Each major entity (Stock, Item, Package, Goods Receipt, Delivery, etc.) has clear one-to-many or many-to-many relationships that define the operational workflow of the Warehouse system.

---

## 🧰 Schema Maintenance

All database changes must be **tracked** and **version-controlled** to ensure consistency across all environments.

### 📄 Raw SQL Scripts

- Schema changes are delivered as **raw SQL**.  
- All such scripts must be placed in `project-folder/sql.txt`, clearly labeled with the **date**, **description**, and **developer name**.  
- These scripts are executed manually on **staging** and **production** environments *after approval*.

### 🚫 Production Policy

- **Manual changes** directly on the production database are **strictly prohibited**.  
- All updates must go through **versioned migrations** or approved **SQL scripts**.

---

## 🧩 Best Practice Tips

- When adding new relationships, always update both the **Model** and the **ERD diagram**.  
- Use Laravel’s **Eloquent relationships** consistently (`hasMany`, `belongsTo`, `belongsToMany`, etc.).  
- Keep the database schema **synchronized** with **seeders** and **factories** to simplify testing and data generation.

> 💡 Maintaining schema discipline ensures that every developer and environment works from the same database foundation, minimizing deployment risks and data inconsistencies.
