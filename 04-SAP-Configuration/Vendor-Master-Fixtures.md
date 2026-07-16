# Vendor Master - Fixtures

## Overview

This document describes the creation of two approved vendors for the procurement of **PCB Assembly Fixtures** in SAP S/4HANA. Since fixture procurement follows a strategic sourcing process, multiple vendors are maintained to support Request for Quotation (RFQ), quotation evaluation, vendor comparison, and supplier selection.

---

## Business Requirement

To ensure competitive procurement and cost optimization, two qualified vendors were created for supplying PCB Assembly Fixtures. These vendors will participate in the RFQ process, allowing quotation comparison before selecting the most suitable supplier.

---

## Transaction Codes

| Activity | Transaction Code |
|----------|------------------|
| Create Business Partner | BP |
| Change Business Partner | BP |
| Display Business Partner | BP |

---

# Organization Details

| Field | Value |
|------|------|
| Company | NT01 |
| Company Code | NT0100 |
| Plant | CN01 |
| Purchasing Organization | POR1 |
| Purchasing Group | PRD |
| Material Category | Fixtures |

---

# Vendor 1 - Wowtop Technologies Pvt. Ltd.

### Vendor Details

| Field | Value |
|------|------|
| Vendor Name | Wowtop Technologies Pvt. Ltd. |
| Location | Bangalore, Karnataka |
| Procurement Category | PCB Assembly Fixtures |
| Purchasing Group | PRD |

The vendor master was created by maintaining the required business partner information, purchasing data, and company code details.

---

## Step 1 - Business Partner Basic Data

Basic information including vendor name, address, communication details, and purchasing information was maintained.

### Screenshot

![Vendor 1 Basic Data](../assets/Vendor%20Master/FIXTURES/Vendor-1/Vendor-1-BP-Initial-Screen-Basic-Data.png)

---

## Step 2 - Company Code / Finance Data

Financial accounting information required for procurement transactions was maintained for the vendor.

### Screenshot

![Vendor 1 Finance Data](../assets/Vendor%20Master/FIXTURES/Vendor-1/Vendor-1-Finance-Data.png)

---

## Step 3 - Vendor Created Successfully

The business partner was successfully created and assigned the Vendor role for procurement activities.

### Screenshot

![Vendor 1 Created](../assets/Vendor%20Master/FIXTURES/Vendor-1/Vendor-1-Vendor-Created.png)

---

# Vendor 2 - Foxconn Precision Engineering

### Vendor Details

| Field | Value |
|------|------|
| Vendor Name | Foxconn Precision Engineering |
| Location | Anna Nagar, Chennai |
| Procurement Category | PCB Assembly Fixtures |
| Purchasing Group | PRD |

A second approved vendor was created to support quotation comparison and competitive sourcing.

---

## Step 4 - Business Partner Basic Data

Vendor master basic information was maintained for the second supplier.

### Screenshot

![Vendor 2 Basic Data](../assets/Vendor%20Master/FIXTURES/Vendor-2/Vendor-2-BP-Initial-Screen-Basic-Data.png)

---

## Step 5 - Company Code / Finance Data

Company code and financial accounting information was maintained.

### Screenshot

![Vendor 2 Finance Data](../assets/Vendor%20Master/FIXTURES/Vendor-2/Vendor-2-Finance-Data.png)

---

## Step 6 - Vendor Created Successfully

The second vendor was successfully created and is available for procurement activities.

### Screenshot

![Vendor 2 Created](../assets/Vendor%20Master/FIXTURES/Vendor-2/Vendor-2-Vendor-Created.png)

---

# Vendor List

Both vendors were successfully created and are available in the SAP Vendor Master.

This vendor list will be used during the RFQ and quotation process.

### Screenshot

![Vendor List](../assets/Vendor%20Master/FIXTURES/Vendor-2/List-of-vendors-display.png)

---

# Vendor Summary

| Vendor | Location | Category | Status |
|---------|----------|----------|--------|
| Wowtop Technologies Pvt. Ltd. | Bangalore | PCB Assembly Fixtures | ✅ Active |
| Foxconn Precision Engineering | Anna Nagar, Chennai | PCB Assembly Fixtures | ✅ Active |

---

# Business Benefits

- Supports competitive procurement through multiple approved vendors.
- Enables Request for Quotation (RFQ) processing.
- Facilitates quotation evaluation and vendor comparison.
- Improves supplier selection based on pricing and delivery performance.
- Ensures procurement transparency and cost optimization.

---

# Conclusion

Two approved vendors were successfully created for **PCB Assembly Fixture** procurement in SAP S/4HANA. Maintaining multiple vendors enables the organization to execute a strategic sourcing process through RFQs, quotation comparison, and informed vendor selection before creating the Purchase Order.

These vendors will be used in the subsequent procurement activities, including **Request for Quotation (ME41), Vendor Quotation (ME47), Price Comparison (ME49), Purchase Order (ME21N), Goods Receipt (MIGO), and Invoice Verification (MIRO)**.

---

# Document Information

| Item | Details |
|------|---------|
| Module | SAP S/4HANA Materials Management (MM) |
| Business Process | Vendor Master |
| Transaction Code | BP |
| Project | SAP S/4HANA MM Greenfield Implementation |
| Document Type | Master Data Documentation |
| Status | ✅ Completed |