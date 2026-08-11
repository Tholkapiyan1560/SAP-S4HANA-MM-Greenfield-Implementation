# Consignment Procurement – Business Scenario

## Business Requirement

The manufacturing organization has two primary methods for procuring raw materials.

### 1. Direct Procurement

Materials are purchased directly from regular suppliers through the standard SAP procurement process.

```text
Requirement
     ↓
PR
     ↓
PO
     ↓
Goods Receipt
     ↓
Company-Owned Stock
```

### 2. Consignment Procurement

For critical materials, the company also works with a third-party supply-chain partner, **JUSDA**.

JUSDA purchases materials from the same suppliers in bulk and maintains the materials in its warehouse as **vendor-owned consignment stock**.

When the company has an urgent requirement and the regular procurement shipment has not arrived, the required materials can be obtained from JUSDA's available consignment stock.

---

# Business Problem

The regular procurement process may not always satisfy urgent production requirements.

For example:

```text
Regular Supplier Shipment
          │
          ▼
     Shipment Delayed
          │
          ▼
   Production Requirement
          │
          ▼
   Material Needed Urgently
```

Waiting for the regular shipment could result in:

- Production delays
- Line stoppage risk
- Emergency procurement
- Increased procurement lead time
- Additional operational costs

To reduce this risk, JUSDA maintains selected raw materials in advance.

---

# Proposed Business Solution

JUSDA maintains bulk quantities of required materials in its warehouse.

The company does not immediately purchase the entire quantity.

Instead, the materials remain under **vendor ownership** until the company requires them.

When an urgent requirement occurs, only the required quantity is transferred from JUSDA's consignment stock to company-owned stock.

---

# Example Scenario

JUSDA maintains the following materials:

| Material | Requirement | Action |
|---|---:|---|
| Material A | 0 | Remains in Consignment |
| Material B | 500 KG | Transfer to Own Stock |
| Material C | 300 KG | Transfer to Own Stock |

The company does not need to take Materials A, B, and C together.

Only the required quantities of **B and C** are transferred.

```text
                 JUSDA Warehouse
                       │
          Vendor Consignment Stock
                       │
             ┌─────────┼─────────┐
             │         │         │
             ▼         ▼         ▼
        Material A  Material B  Material C
             │         │         │
             │         ▼         ▼
             │       411 K     411 K
             │         │         │
             │         └────┬────┘
             │              ▼
             │       Company-Owned Stock
             │
             ▼
       Remains with Vendor
```

---

# SAP Business Process

The business requirement is represented in SAP as follows:

```text
Material Requirement
        │
        ▼
Material Master
        │
        ▼
JUSDA Vendor Master
        │
        ▼
Consignment Info Record
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
Urgent Material Requirement
        │
        ▼
MIGO – 411 K
        │
        ▼
Company-Owned Stock
        │
        ▼
MMBE
Stock Verification
        │
        ▼
MRM1 / MRKO
Vendor Settlement
```

---

# SAP Consignment Process

## Consignment Purchase Order

The Purchase Order is created using:

```text
Item Category: K – Consignment
```

This identifies the material as vendor consignment stock.

---

## Goods Receipt

The material is received into the company's available consignment stock while ownership remains with the vendor.

The stock is therefore maintained separately from normal company-owned inventory.

---

## Transfer to Own Stock

When the material is required for production, the required quantity is transferred using:

```text
Movement Type: 411 K
```

The transfer changes the stock ownership from:

```text
Vendor Consignment Stock
          ↓
Company-Owned Stock
```

Only the required quantity is transferred.

---

# Stock Visibility

After the transfer, **MMBE** is used to verify the stock position.

The system provides visibility of:

- Vendor Consignment Stock
- Unrestricted Company Stock
- Material Quantity
- Plant
- Storage Location

This allows the procurement team to verify the stock movement and ownership change.

---

# Vendor Settlement

After the required quantity is transferred from consignment stock, the corresponding vendor settlement process is executed using:

```text
MRM1
   ↓
MRKO
```

The settlement process ensures that the vendor is compensated for the quantity transferred from vendor-owned consignment stock.

---

# Business Controls

The process provides control over:

- Vendor-owned inventory
- Material ownership
- Actual quantity transferred
- Stock availability
- Urgent material withdrawals
- Vendor settlement quantities

---

# Expected Business Outcome

The Consignment Procurement process provides the organization with an additional procurement channel for critical raw materials.

It enables the company to:

- Maintain production continuity
- Access urgently required materials
- Utilize vendor-managed inventory
- Transfer only the required quantity to company ownership
- Maintain clear stock ownership visibility
- Settle the vendor based on the relevant transferred quantity

---

# Scenario Conclusion

The implemented SAP S/4HANA MM process demonstrates how **Consignment Procurement** can be integrated into a manufacturing procurement strategy alongside standard direct purchasing.

The solution provides a controlled mechanism for handling urgent material requirements while maintaining clear ownership, stock visibility, and vendor settlement.

**Business Principle:**

> Maintain availability through vendor-owned stock and take ownership only when the material is required.