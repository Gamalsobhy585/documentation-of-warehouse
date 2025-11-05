---
title: What is Warehouse?
nav_order: 1
---

# What is Warehouse?

The **Warehouse module** is designed to serve storekeepers and warehouse staff by simplifying and organizing all warehouse operations.

It provides a structured system for managing master data — including **stocks, substocks, categories, subcategories, items, and packages** — ensuring smooth daily operations such as receiving, issuing, transferring, and inventory adjustments.

---

## 🧱 Master Data Structure

### 1. Stock
Represents a **main warehouse location**, which may consist of multiple buildings, sections, or shelters.  
Each stock can have several substocks.

### 2. Substock
Represents an **internal division** within a main stock — for example, a hall, zone, or storage area.

### 3. Category / Subcategory
Defines the **classification hierarchy** of stored materials.  
Example: `Pipes → Welding Pipes`.

### 4. Item
Each item belongs to a specific category and subcategory, describing the **material type and its general properties**.  
Example: *Imported Pipe – Diameter 4 inch.*

### 5. Package
Defines detailed attributes such as **size, dimensions, or unit of measurement**.  
Example: *Imported Welding Pipe Ø4 inch × 6m.*

> This structure enables accurate tracking of every material by its type, category, and physical specification — making warehouse operations faster, clearer, and less prone to errors.

---

## 🚚 Item Delivery (إذن التسليم)

The **Delivery Item** represents the initial stage of receiving materials into the warehouse.  
It records details provided by the supplier or delivery driver upon arrival — including quantities, weights, and delivery notes.

After arrival, materials are inspected by the warehouse or quality team, who verify whether received quantities and weights match the supplier’s declaration, noting any shortages, excess, or damages.

If necessary, the MRP or responsible engineer can also add remarks related to the delivery.  
This stage ensures that all incoming materials are properly recorded before being officially added to stock.

---

## 📦 Goods Receipt (إذن الإضافة)

The **Goods Receipt** is created based on an approved Delivery Item.  
The warehouse officer selects the related delivery note and specifies the exact items and quantities to be added to stock.

This process passes through an **approval cycle** to verify correctness and authorization.  
If any items include an expiry date, it is recorded here; otherwise, it’s skipped.

Once approved, the confirmed quantities are posted to inventory — updating balances and making materials available for use.

---

## 🧾 Item Issue Request (طلب الصرف)

The **Item Issue Request** is a formal request for materials from the warehouse.  
The requester specifies the required items and quantities for a specific task or project.

Each request passes through an **approval cycle** to confirm that the requested materials are justified before release from stock.

---

## 📤 Goods Issue Note (إذن الصرف)

Once a **Material Request** is approved, a **Goods Issue Note** is created based on it.  
This document shows approved quantities and serves as the **official authorization** to release materials.

When confirmed, the system automatically deducts the issued quantities from inventory, updates item balances, and records the movement in the transaction log — ensuring **full traceability and accuracy**.

---

## 🔁 Item Transfer (إذن التحويل)

The **Item Transfer** is used to move materials between substocks within the same warehouse.  
It allows staff to reallocate items between storage areas (e.g., from Substock A to Substock B) to balance inventory, optimize space, or meet project needs.

Currently, transfers are supported only **within the same warehouse**.  
Future versions will support inter-warehouse transfers.

Each transfer updates both the **source** and **destination** substocks, keeping total stock quantities consistent and traceable.

---

## ↩️ Goods Return (إذن الارتجاع)

The **Goods Return** process is used when previously issued materials are partially or fully returned because they were not consumed.

Users specify the returned quantities — by count or measurement — ensuring unused materials are correctly recorded back into stock.

In some cases, the returned material may have **different dimensions** (e.g., a cut pipe).  
The return process supports recording such variations accurately.

Once confirmed, the returned quantities are added back to inventory, updating balances and logging the transaction for **full traceability**.
