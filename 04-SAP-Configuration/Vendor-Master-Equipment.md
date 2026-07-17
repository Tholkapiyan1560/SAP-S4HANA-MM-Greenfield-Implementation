# Equipment Vendor Master

## Objective

This document describes the creation of the Equipment Vendor Master in SAP S/4HANA MM using Business Partner (BP) transaction. The vendor supplies AOI (Automated Optical Inspection) Machines required for SMT production lines.

---

# Vendor Details

| Field | Value |
|-------|-------|
| Vendor Name | ASM Technologies Pvt Ltd, Mumbai |
| Vendor Type | Equipment Supplier |
| Business Partner Role | FLVN00 – FI Vendor |
| Company Code | NT01 |
| Purchasing Organization | PO01 |
| Purchasing Group | EQP |
| City | Mumbai |
| State | Maharashtra |
| Country | India |
| Industry | Electronics Manufacturing Equipment |
| Equipment Supplied | AOI Machine (Automated Optical Inspection) |
| Payment Method | Bank Transfer |
| Currency | INR |

---

# Step 1 – Business Partner Initial Screen

**Transaction Code:** `BP`

Create a new Business Partner using the **FLVN00 (FI Vendor)** role.

Configure the vendor as an organization and enter the general company information.

### Screenshot

![BP Initial Screen Basic Data](../assets/Vendor%20Master/EQUIPMENT/BP-Initial-Screen-Basic-Data.png)

---

# Step 2 – Finance Data

Maintain the finance-related information required for Accounts Payable.

Information maintained:

- Company Code
- Reconciliation Account
- Payment Terms
- Payment Method
- Currency
- Tax Details

### Screenshot

![Vendor Created with Finance Data](../assets/Vendor%20Master/EQUIPMENT/Vendor-Created-with-Finance-Data.png)

---

# Step 3 – Vendor Created Successfully

After maintaining all mandatory Business Partner and Finance information, save the vendor.

SAP generates the Business Partner/Vendor Number successfully.

### Screenshot

![Vendor Created Successfully](../assets/Vendor%20Master/EQUIPMENT/Vendor-Created-Successfully.png)

---

# Step 4 – Vendor Display

Display the created vendor to verify all master data.

Verification includes:

- General Information
- Address
- Company Code Data
- Vendor Role
- Finance Data

### Screenshot

![Vendor Display](../assets/Vendor%20Master/EQUIPMENT/Vendor-Display.png)

---

# Business Benefits

- Centralized Vendor Master Management
- Supports Equipment Procurement Process
- Enables Purchase Requisition Processing
- Supports Purchase Order Creation
- Enables Goods Receipt Processing
- Supports Invoice Verification
- Integrates with SAP Finance (FI)

---

# Summary

The Equipment Vendor Master for **ASM Technologies Pvt Ltd, Mumbai** has been successfully created in SAP S/4HANA MM. The vendor is now available for procurement activities including Purchase Requisition, Purchase Order, Goods Receipt, and Invoice Verification as part of the Procure-to-Pay (P2P) process.