---
title: Module Integration
nav_order: 4
---

# Connecting the Warehouse with Other Modules

The **Warehouse module** connects with other modules through well-defined **integration points** that ensure **data consistency** and **workflow automation** across the system.

It communicates with other parts of the ERP through several mechanisms:

---

## 🔗 1. API Integration

Modules such as **Purchasing**, **Projects**, or **Finance** can interact with the Warehouse via **RESTful APIs** to create, read, or update warehouse documents (e.g., *Delivery Items*, *Goods Receipts*, *Goods Issues*).

This enables seamless data exchange between modules while maintaining strict access control and data integrity.

---

## 🧾 2. Reference Linking

Each warehouse transaction stores a `reference_type` and `reference_id` — for example, linking a **Goods Receipt** to its **Purchase Order**.

This allows every material movement to be **traced back** to its original source document in another module, ensuring full visibility and traceability.

---

## ⚙️ 3. Event-Based Communication

The system can trigger **domain events** such as:
- `GoodsReceived`
- `GoodsIssued`

Other modules listen to these events to update their data automatically — **no manual synchronization required**.

This approach keeps the system reactive and always up to date.

---

## 🧑‍💼 4. Approval Workflow Sharing

The Warehouse module participates in **shared approval workflows** with other modules.

For example:
- A **Project Manager** or **Finance Officer** may need to approve a *Goods Issue* before it’s finalized.
- Approval logic is centralized and reusable across modules.

This ensures accountability and cross-departmental validation.

---

## 🧩 5. Shared Master Data

Core entities such as **Items**, **Units**, and **Suppliers** are shared across multiple modules.  
This keeps all systems **synchronized** and eliminates **data duplication**.

---

## 🌐 Summary

Together, these integration methods allow the Warehouse module to operate as a **central hub**, ensuring seamless coordination between **Purchasing**, **Projects**, **Finance**, and other business modules.

> 💡 The goal is simple: **one source of truth** for all material and stock-related operations across the organization.
