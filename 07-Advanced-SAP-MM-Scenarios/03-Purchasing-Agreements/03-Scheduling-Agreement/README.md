# 03 – Scheduling Agreement

## Overview

A **Scheduling Agreement** is a long-term purchasing agreement between an organization and a supplier in which the overall material requirement is agreed in advance and deliveries are planned through **schedule lines**.

Unlike a standard purchase order, a Scheduling Agreement allows the organization to define multiple delivery dates and quantities against the same purchasing agreement.

In this scenario, the Scheduling Agreement is created for **14,000 EA**, with the quantity distributed across two scheduled deliveries of **7,000 EA each**.

---

## Process Objective

The objective of this process is to demonstrate the complete procurement cycle for a Scheduling Agreement, starting from agreement creation through delivery scheduling, Goods Receipt, and Invoice Verification.

The process covers:

```text
ME31L
   ↓
Scheduling Agreement Creation
   ↓
ME38
   ↓
Delivery Schedule
   ↓
MIGO
   ↓
Goods Receipt
   ↓
MIRO
   ↓
Invoice Verification
```

---

## Business Scenario

The organization requires **14,000 EA** of `BARE_PCB_BOARD` from the supplier.

Instead of receiving the complete quantity at once, the requirement is divided into two scheduled deliveries:

| Schedule Line | Delivery Date |      Quantity |
| ------------- | ------------- | ------------: |
| 1             | 16.08.2026    |      7,000 EA |
| 2             | 31.08.2026    |      7,000 EA |
| **Total**     |               | **14,000 EA** |

This allows the supplier to deliver the material according to the organization's planned requirement.

---

## Scheduling Agreement Details

| Field                   | Value                      |
| ----------------------- | -------------------------- |
| Scheduling Agreement    | 7000000016                 |
| Agreement Type          | LP                         |
| Supplier                | 7000010015                 |
| Supplier Name           | JUSDA CORPORATIONS PVT LTD |
| Company Code            | NT01                       |
| Purchasing Organization | POR1                       |
| Purchasing Group        | CS0                        |
| Plant                   | CN01                       |
| Storage Location        | CS01                       |
| Material                | BARE_PCB_BOARD             |
| Material Description    | BARE PCB MOTHER BOARD      |
| Target Quantity         | 14,000 EA                  |
| Net Price               | 500.00 INR                 |
| Validity Start          | 16.08.2026                 |
| Validity End            | 15.08.2027                 |
| Currency                | INR                        |
| Payment Terms           | 0001                       |

---

## 1. Scheduling Agreement Creation

### Transaction Code

`ME31L`

The Scheduling Agreement is created by maintaining:

* Supplier
* Agreement Type
* Purchasing Organization
* Purchasing Group
* Plant
* Storage Location
* Validity Period
* Material
* Target Quantity
* Net Price

The total target quantity is maintained as:

**14,000 EA**

After entering the required information, the Scheduling Agreement is saved and SAP generates the agreement number.

**Scheduling Agreement: `7000000016`**

---

## 2. Delivery Schedule Maintenance

### Transaction Code

`ME38`

After creating the Scheduling Agreement, the delivery schedule is maintained using `ME38`.

The total target quantity of **14,000 EA** is divided into two schedule lines:

| Delivery Date | Scheduled Quantity |
| ------------- | -----------------: |
| 16.08.2026    |           7,000 EA |
| 31.08.2026    |           7,000 EA |
| **Total**     |      **14,000 EA** |

The schedule lines determine when the supplier is expected to deliver the agreed quantities.

---

## 3. Goods Receipt

### Transaction Code

`MIGO`

Goods Receipt is performed against the Scheduling Agreement using movement type `101`.

The first scheduled delivery is:

**16.08.2026 → 7,000 EA**

The second scheduled delivery is:

**31.08.2026 → 7,000 EA**

If the second delivery is attempted before its scheduled date, SAP may not provide the schedule line as a selectable item depending on the configured delivery controls.

The Goods Receipt process demonstrates how the delivery schedule maintained through `ME38` controls the expected receipt quantities and dates.

---

## 4. Invoice Verification

### Transaction Code

`MIRO`

After Goods Receipt, the supplier invoice is processed using `MIRO`.

The Scheduling Agreement number `7000000016` is entered as the purchasing document reference.

The invoice is verified against the relevant purchasing document and Goods Receipt before posting.

The process includes:

```text
MIRO
   ↓
Enter Invoice Details
   ↓
Reference Scheduling Agreement
   ↓
Retrieve Invoice Item
   ↓
Enter / Verify Amount
   ↓
Calculate Tax
   ↓
Simulate
   ↓
Review Accounting Entries
   ↓
Post Invoice
```

---

## 5. Complete Process Flow

```text
ME31L
   ↓
Create Scheduling Agreement
   ↓
Target Quantity: 14,000 EA
   ↓
Scheduling Agreement
7000000016
   ↓
ME38
   ↓
Maintain Delivery Schedule
   ↓
16.08.2026 → 7,000 EA
31.08.2026 → 7,000 EA
   ↓
MIGO
   ↓
Goods Receipt – 7,000 EA
   ↓
MIGO
   ↓
Second Delivery – 7,000 EA
   ↓
MIRO
   ↓
Invoice Verification
   ↓
Simulate
   ↓
Post Invoice
   ↓
Procurement Process Completed
```

---

## 6. Transactions Used

| Process                       | Transaction Code | Purpose                          |
| ----------------------------- | ---------------- | -------------------------------- |
| Scheduling Agreement Creation | `ME31L`          | Create Scheduling Agreement      |
| Scheduling Agreement Schedule | `ME38`           | Maintain delivery schedule       |
| Goods Receipt                 | `MIGO`           | Post Goods Receipt               |
| Invoice Verification          | `MIRO`           | Verify and post supplier invoice |

---

## 7. Key Business Concept

The key advantage of a Scheduling Agreement is that a **single long-term purchasing agreement can contain multiple planned deliveries**.

In this scenario:

**14,000 EA total requirement**

is divided into:

**7,000 EA on 16.08.2026**

and

**7,000 EA on 31.08.2026**

This provides better control over supplier deliveries, inventory planning, Goods Receipt processing, and invoice verification.

---

## Documentation Structure

```text
03-Scheduling-Agreement/
│
├── README.md
├── Agreement-Creation.md
├── Goods-Receipt.md
├── Invoice-Verification.md
└── Business-Rules.md
```

The Scheduling Agreement documentation therefore covers the complete process from **agreement creation → delivery scheduling → Goods Receipt → Invoice Verification**, using SAP S/4HANA Materials Management.
