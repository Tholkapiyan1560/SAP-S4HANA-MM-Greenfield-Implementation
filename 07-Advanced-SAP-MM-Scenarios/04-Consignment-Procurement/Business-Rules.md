# Consignment Procurement Business Rules

## Objective

The purpose of this document is to define the business rules governing the complete Consignment Procurement process from supplier and material setup through consignment purchasing, goods receipt, stock ownership transfer and vendor settlement.

---

# Business Scenario

The following business rules were defined and validated for the Consignment Procurement process.

| Business Rule | Process / Transaction | Status |
|---|---|---|
| Consignment Purchasing Information Record must be maintained | PIR | ✅ Valid |
| Consignment Purchase Order must use Item Category K | ME21N | ✅ Valid |
| Goods Receipt must be posted using Movement Type 101 | MIGO – 101 | ✅ Valid |
| Received material must remain supplier-owned after Goods Receipt | MMBE | ✅ Valid |
| Consignment stock must be identifiable before ownership transfer | MMBE | ✅ Valid |
| Ownership transfer must use Movement Type 411 K | MIGO – 411 K | ✅ Valid |
| Transferred material must become company-owned unrestricted stock | MMBE | ✅ Valid |
| Consignment withdrawal must be available for vendor settlement | MRKO | ✅ Valid |
| Unsettled withdrawals must be identified before settlement | MRKO | ✅ Valid |
| Consignment withdrawal must be settled with the supplier | MRKO | ✅ Valid |

---

# Business Rules

The following business rules apply to the Consignment Procurement process.

- A valid Consignment Purchasing Information Record must exist for the supplier and material combination before the Consignment Procurement process is executed.

- The Consignment Purchase Order must be created with Item Category `K – Consignment` so that the material is treated as supplier-owned consignment stock.

- Goods Receipt for the Consignment Purchase Order must be posted using Movement Type `101` against the relevant Purchase Order.

- After Goods Receipt, the material may be physically available at the company's plant and storage location, but ownership must remain with the supplier until the material is withdrawn for company use.

- Consignment stock must be verified in MMBE before the ownership transfer to ensure that the material is available as supplier-owned stock.

- When the company requires the consignment material for its own use, the ownership transfer must be performed using Movement Type `411 K`.

- After the `411 K` transfer, the transferred quantity must become company-owned stock and must be visible under **Unrestricted Use** in MMBE.

- The consignment withdrawal created through the ownership transfer must be available in MRKO for supplier settlement.

- Only relevant unsettled consignment withdrawals should be selected for settlement so that previously settled withdrawals are not processed again.

- The supplier settlement must be successfully processed through MRKO, resulting in the creation of the corresponding settlement document for the withdrawn consignment quantity.

---

# Key Business Rules

The key ownership and inventory rules are summarized below.

```text
Consignment Purchase Order
        ↓
Goods Receipt – 101
        ↓
Supplier-Owned Consignment Stock
        ↓
Company Requires Material
        ↓
Transfer Posting – 411 K
        ↓
Company-Owned Stock
        ↓
Unrestricted Use
        ↓
Consignment Withdrawal
        ↓
MRKO Vendor Settlement