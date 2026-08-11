# Consignment Procurement – SAP S/4HANA MM

## Overview

This project implements an end-to-end **Consignment Procurement** scenario in SAP S/4HANA Materials Management (MM), based on a realistic manufacturing procurement requirement.

The scenario addresses a business model where the company has two procurement channels for raw materials:

1. **Direct Procurement** – Materials are purchased directly from regular suppliers through SAP.
2. **Consignment Procurement** – Materials are made available through a third-party partner, **JUSDA**, which purchases and stores bulk quantities from the same suppliers in advance.

When the company's regular procurement shipment is delayed or an urgent material requirement occurs, the required quantity can be withdrawn from JUSDA's consignment stock instead of waiting for the regular shipment.

---

## Business Objective

The objective is to demonstrate how SAP S/4HANA MM can manage **vendor-owned inventory** and transfer only the required quantity into company-owned stock when the material is actually needed.

This approach helps the business:

- Reduce production interruptions
- Improve material availability
- Avoid unnecessary emergency procurement
- Maintain vendor-owned stock until consumption/withdrawal
- Pay the vendor based on the quantity transferred from consignment stock
- Improve procurement flexibility during supply disruptions

---

## End-to-End Process

```text
Business Requirement
        │
        ▼
Material Master
        │
        ▼
Vendor Master – JUSDA
        │
        ▼
Consignment Purchase Info Record
        │
        ▼
Purchase Requisition
        │
        ▼
Consignment Purchase Order
(Item Category K)
        │
        ▼
MIGO – Goods Receipt
        │
        ▼
Vendor Consignment Stock
        │
        ▼
MIGO – Transfer Posting
Movement Type 411 K
        │
        ▼
Company-Owned Stock
        │
        ▼
MMBE – Stock Verification
        │
        ▼
MRM1
        │
        ▼
MRKO
Vendor Settlement
```

---

## SAP Process Coverage

| Process Area | SAP Transaction | Purpose |
|---|---|---|
| Material Master | `MM01` | Create procurement material |
| Vendor Master | `BP` | Create JUSDA as vendor |
| Consignment PIR | `ME11` | Maintain consignment purchasing conditions |
| Purchase Requisition | `ME51N` | Create material requirement |
| Purchase Order | `ME21N` | Create Consignment PO |
| Goods Receipt | `MIGO` | Receive material into vendor consignment stock |
| Transfer Posting | `MIGO – 411 K` | Transfer consignment stock to own stock |
| Stock Verification | `MMBE` | Verify stock ownership and quantity |
| Settlement | `MRM1 / MRKO` | Process vendor settlement |

---

## Consignment Stock Concept

In Consignment Procurement, the material is physically available at the company's location but remains **vendor-owned** until it is transferred to company-owned stock.

```text
                 Vendor-Owned Stock
                        │
                        │
                 Material Available
                        │
                        ▼
                 Urgent Requirement
                        │
                        ▼
                 MIGO – 411 K
                        │
                        ▼
                Company-Owned Stock
                        │
                        ▼
                 Vendor Settlement
```

This allows the company to maintain material availability without immediately taking ownership of the entire consignment quantity.

---

## Key SAP Concept

### Item Category `K` – Consignment

The Consignment Purchase Order uses **Item Category K**.

This identifies the procurement process as vendor consignment rather than standard purchase procurement.

The material received through the consignment process remains under vendor ownership until the required quantity is transferred to company-owned stock.

---

## Business Scenario Example

Assume JUSDA maintains bulk quantities of Materials **A, B, and C** in its warehouse.

The company has an urgent requirement for:

```text
Material A → Not Required
Material B → Required
Material C → Required
```

Instead of purchasing the entire requirement again, the company withdraws only Materials **B and C** from JUSDA's available consignment stock.

```text
JUSDA Consignment Stock

Material A ─────────────── Remains with Vendor
Material B ─────────────── Transfer to Own Stock
Material C ─────────────── Transfer to Own Stock
```

The company is therefore able to respond to the urgent requirement without waiting for the regular supplier shipment.

---

## Key Business Benefits

### Supply Continuity
Provides an alternative source of material during procurement delays.

### Inventory Flexibility
Vendor-owned inventory can be maintained without immediately becoming company-owned inventory.

### Reduced Production Risk
Urgent material requirements can be fulfilled without waiting for regular purchase shipments.

### Controlled Vendor Settlement
The vendor is settled based on the quantity transferred from consignment stock.

### Better Procurement Visibility
SAP provides visibility of vendor consignment stock and company-owned stock separately.

---

## Implementation Scope

This implementation covers:

- Material Master
- Vendor Master
- Consignment Purchasing Info Record
- Purchase Requisition
- Consignment Purchase Order
- Goods Receipt
- Consignment Stock
- Transfer Posting `411 K`
- Stock Verification through `MMBE`
- Vendor Settlement
- Business Rules
- Functional Testing

---

## Project Outcome

The Consignment Procurement process demonstrates how SAP S/4HANA MM can support a manufacturing organization in managing **vendor-owned inventory, urgent material requirements, stock ownership transfer, and vendor settlement** within a controlled procurement process.

This scenario forms part of my **Advanced SAP S/4HANA MM Greenfield Implementation Portfolio**.

---