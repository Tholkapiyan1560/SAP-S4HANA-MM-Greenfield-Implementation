# Vendor Master - Consumables

## Overview

This document describes the creation of the Vendor Master for Consumable Materials using the **Business Partner (BP)** transaction in SAP S/4HANA.

The Vendor Master is a core master data object in SAP Materials Management (MM). It enables procurement activities such as Purchase Requisition (PR), Purchase Order (PO), Goods Receipt (GR), and Invoice Verification (MIRO).

---

## Business Requirement

NovaTech Electronics Manufacturing Pvt. Ltd. procures consumable materials such as SMT Wiper Rolls, Gloves, Wipe Rolls, Milling Cutters, ESD Consumables, and Packaging Materials from approved suppliers.

To support procurement activities, a Vendor Master was created using the Business Partner (BP) transaction.

---

## Transaction Code

| Activity | Transaction Code |
|----------|------------------|
| Create Vendor | BP |
| Display Vendor | BP |

---

## Organization Details

| Field | Value |
|------|------|
| Company | NT01 |
| Company Code | NT0100 |
| Plant | CN01 |
| Purchasing Organization | POR1 |
| Purchasing Group | CON |
| Vendor Category | Consumables Supplier |

---

# Step 1 - Business Partner Initial Screen

The Business Partner (BP) transaction was used to create the supplier. The supplier category, grouping, and BP role were selected before entering vendor master information.

### Screenshot

![BP Initial Screen](../assets/Vendor%20Master/Consumables/BP-Initial-Screen-Basic%20data.png)

---

# Step 2 - Vendor Financial Data

Financial Accounting (FI) information was maintained for the supplier.

The following details were configured:

- Company Code
- Reconciliation Account
- Payment Terms
- Payment Method
- Financial Accounting Settings

These settings enable invoice posting and vendor payment processing.

### Screenshot

![Vendor Financial Data](../assets/Vendor%20Master/Consumables/Vendor-Created-with-finance-data.png)

---

# Step 3 - Vendor Created Successfully

After maintaining all mandatory supplier information, the Business Partner was successfully created and saved in SAP S/4HANA.

The system generated a confirmation message indicating successful vendor creation.

### Screenshot

![Vendor Created Successfully](../assets/Vendor%20Master/Consumables/Vendor-Created%20Successfully.png)

---

# Step 4 - Vendor Display

The completed Vendor Master was displayed to verify the maintained supplier information.

The vendor is now available for:

- Purchase Requisition (PR)
- Purchase Order (PO)
- Goods Receipt (GR)
- Invoice Verification (MIRO)
- Vendor Evaluation

### Screenshot

![Vendor Display](../assets/Vendor%20Master/Consumables/Vendor-Display.png)

---

# Vendor Configuration Summary

| Configuration | Value |
|--------------|-------|
| Vendor Type | Consumables Supplier |
| Company | NT01 |
| Company Code | NT0100 |
| Plant | CN01 |
| Purchasing Organization | POR1 |
| Purchasing Group | CON |
| Status | ✅ Successfully Created |

---

# Conclusion

The Vendor Master for Consumables was successfully created using the Business Partner (BP) transaction in SAP S/4HANA.

The vendor has been configured with the required organizational, purchasing, and financial data, making it available for procurement activities within the SAP MM module.

This Vendor Master will be used in the subsequent Procure-to-Pay (P2P) process, including Purchase Order creation, Goods Receipt, and Invoice Verification.

---

# Document Information

| Item | Details |
|------|---------|
| Module | SAP S/4HANA Materials Management (MM) |
| Business Process | Vendor Master Creation |
| Project | SAP S/4HANA MM Greenfield Implementation |
| Document Status | ✅ Completed |